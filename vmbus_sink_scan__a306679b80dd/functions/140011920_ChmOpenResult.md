# ChmOpenResult

- ea: `0x140011920`
- end: `0x140011a24`
- name: `ChmOpenResult`
- size: `260`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140010ff8`

## callees

- `0x14000fdc0`
- `0x14000fe8c`
- `0x140010b08`
- `0x1400111ac`
- `0x140011920`
- `0x1400121e4`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall ChmOpenResult(__int64 a1, unsigned int *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rsi
  __int64 v6; // r8
  PDEVICE_OBJECT *result; // rax

  v5 = ChReferenceClientChannel(a1, a2[2]);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF__guid_iDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        v6,
        a1 + 128,
        *(_QWORD *)(a1 + 120),
        a2[2],
        a2[3],
        a2[4]);
    }
    ChClientOpenResult(v5, v4, a2[4]);
    return (PDEVICE_OBJECT *)ChDereferenceChannelInternal(v5, 1, 1451);
  }
  else
  {
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      return (PDEVICE_OBJECT *)WPP_SF__guid_iD(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 14,
                                 WPP_cd971d606b993d56b4145b039062675b_Traceguids,
                                 a1 + 128,
                                 *(_QWORD *)(a1 + 120),
                                 a2[2]);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140011920  mov     [rsp+arg_0], rbx
0x140011925  mov     [rsp+arg_8], rsi
0x14001192a  push    rdi
0x14001192b  sub     rsp, 40h
0x14001192f  mov     rbx, rdx
0x140011932  mov     rdi, rcx
0x140011935  mov     edx, [rdx+8]
0x140011938  call    ChReferenceClientChannel
0x14001193d  mov     rsi, rax
0x140011940  test    rax, rax
0x140011943  jnz     short loc_14001199F
0x140011945  mov     rcx, cs:WPP_GLOBAL_Control
0x14001194c  lea     rax, WPP_GLOBAL_Control
0x140011953  cmp     rcx, rax
0x140011956  jz      loc_140011A13
0x14001195c  test    dword ptr [rcx+2Ch], 80000h
0x140011963  jz      loc_140011A13
0x140011969  cmp     byte ptr [rcx+29h], 2
0x14001196d  jb      loc_140011A13
0x140011973  mov     eax, [rbx+8]
0x140011976  lea     r9, [rdi+80h]
0x14001197d  mov     rcx, [rcx+18h]
0x140011981  lea     edx, [rsi+0Eh]
0x140011984  mov     [rsp+48h+var_20], eax
0x140011988  lea     r8, WPP_cd971d606b993d56b4145b039062675b_Traceguids
0x14001198f  mov     rax, [rdi+78h]
0x140011993  mov     [rsp+48h+var_28], rax
0x140011998  call    WPP_SF__guid_iD
0x14001199d  jmp     short loc_140011A13
0x14001199f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400119a6  lea     rax, WPP_GLOBAL_Control
0x1400119ad  cmp     rcx, rax
0x1400119b0  jz      short loc_1400119F4
0x1400119b2  test    dword ptr [rcx+2Ch], 80000h
0x1400119b9  jz      short loc_1400119F4
0x1400119bb  cmp     byte ptr [rcx+29h], 4
0x1400119bf  jb      short loc_1400119F4
0x1400119c1  mov     eax, [rbx+10h]
0x1400119c4  lea     r9, [rdi+80h]
0x1400119cb  mov     rcx, [rcx+18h]
0x1400119cf  mov     edx, 0Fh
0x1400119d4  mov     [rsp+48h+var_10], eax
0x1400119d8  mov     eax, [rbx+0Ch]
0x1400119db  mov     [rsp+48h+var_18], eax
0x1400119df  mov     eax, [rbx+8]
0x1400119e2  mov     [rsp+48h+var_20], eax
0x1400119e6  mov     rax, [rdi+78h]
0x1400119ea  mov     [rsp+48h+var_28], rax
0x1400119ef  call    WPP_SF__guid_iDDD
0x1400119f4  mov     r8d, [rbx+10h]
0x1400119f8  mov     rcx, rsi
0x1400119fb  call    ChClientOpenResult
0x140011a00  mov     edx, 1
0x140011a05  mov     r8d, 5ABh
0x140011a0b  mov     rcx, rsi
0x140011a0e  call    ChDereferenceChannelInternal
0x140011a13  mov     rbx, [rsp+48h+arg_0]
0x140011a18  mov     rsi, [rsp+48h+arg_8]
0x140011a1d  add     rsp, 40h
0x140011a21  pop     rdi
0x140011a22  retn
```
