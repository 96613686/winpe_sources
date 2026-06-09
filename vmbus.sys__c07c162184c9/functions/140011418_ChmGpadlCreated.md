# ChmGpadlCreated

- ea: `0x140011418`
- end: `0x140011523`
- name: `ChmGpadlCreated`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140010ff8`

## callees

- `0x14000eec8`
- `0x14000fdc0`
- `0x14000fe8c`
- `0x1400111ac`
- `0x140011418`
- `0x1400121e4`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall ChmGpadlCreated(__int64 a1, unsigned int *a2)
{
  __int64 v4; // rsi
  __int64 v5; // r8
  PDEVICE_OBJECT *result; // rax

  v4 = ChReferenceClientChannel(a1, a2[2]);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF__guid_iDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        v5,
        a1 + 128,
        *(_QWORD *)(a1 + 120),
        a2[2],
        a2[3],
        a2[4]);
    }
    ChGpadlCreated(a1, v4, a2[3], a2[4]);
    return (PDEVICE_OBJECT *)ChDereferenceChannelInternal(v4, 2, 1509);
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
                                 16,
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
0x140011418  mov     [rsp+arg_0], rbx
0x14001141d  mov     [rsp+arg_8], rsi
0x140011422  push    rdi
0x140011423  sub     rsp, 40h
0x140011427  mov     rbx, rdx
0x14001142a  mov     rdi, rcx
0x14001142d  mov     edx, [rdx+8]
0x140011430  call    ChReferenceClientChannel
0x140011435  mov     rsi, rax
0x140011438  test    rax, rax
0x14001143b  jnz     short loc_140011497
0x14001143d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011444  lea     rax, WPP_GLOBAL_Control
0x14001144b  cmp     rcx, rax
0x14001144e  jz      loc_140011512
0x140011454  test    dword ptr [rcx+2Ch], 80000h
0x14001145b  jz      loc_140011512
0x140011461  cmp     byte ptr [rcx+29h], 2
0x140011465  jb      loc_140011512
0x14001146b  mov     eax, [rbx+8]
0x14001146e  lea     r9, [rdi+80h]
0x140011475  mov     rcx, [rcx+18h]
0x140011479  lea     edx, [rsi+10h]
0x14001147c  mov     [rsp+48h+var_20], eax
0x140011480  lea     r8, WPP_cd971d606b993d56b4145b039062675b_Traceguids
0x140011487  mov     rax, [rdi+78h]
0x14001148b  mov     [rsp+48h+var_28], rax
0x140011490  call    WPP_SF__guid_iD
0x140011495  jmp     short loc_140011512
0x140011497  mov     rcx, cs:WPP_GLOBAL_Control
0x14001149e  lea     rax, WPP_GLOBAL_Control
0x1400114a5  cmp     rcx, rax
0x1400114a8  jz      short loc_1400114EC
0x1400114aa  test    dword ptr [rcx+2Ch], 80000h
0x1400114b1  jz      short loc_1400114EC
0x1400114b3  cmp     byte ptr [rcx+29h], 4
0x1400114b7  jb      short loc_1400114EC
0x1400114b9  mov     eax, [rbx+10h]
0x1400114bc  lea     r9, [rdi+80h]
0x1400114c3  mov     rcx, [rcx+18h]
0x1400114c7  mov     edx, 11h
0x1400114cc  mov     [rsp+48h+var_10], eax
0x1400114d0  mov     eax, [rbx+0Ch]
0x1400114d3  mov     [rsp+48h+var_18], eax
0x1400114d7  mov     eax, [rbx+8]
0x1400114da  mov     [rsp+48h+var_20], eax
0x1400114de  mov     rax, [rdi+78h]
0x1400114e2  mov     [rsp+48h+var_28], rax
0x1400114e7  call    WPP_SF__guid_iDDD
0x1400114ec  mov     r9d, [rbx+10h]
0x1400114f0  mov     rdx, rsi
0x1400114f3  mov     r8d, [rbx+0Ch]
0x1400114f7  mov     rcx, rdi
0x1400114fa  call    ChGpadlCreated
0x1400114ff  mov     edx, 2
0x140011504  mov     r8d, 5E5h
0x14001150a  mov     rcx, rsi
0x14001150d  call    ChDereferenceChannelInternal
0x140011512  mov     rbx, [rsp+48h+arg_0]
0x140011517  mov     rsi, [rsp+48h+arg_8]
0x14001151c  add     rsp, 40h
0x140011520  pop     rdi
0x140011521  retn
```
