# CUsbBusFilter::CreateInstance(WDFDEVICE__ *,uchar,void *,CUsbBusFilter * *)

- ea: `0x1400029e4`
- end: `0x140002ad7`
- name: `?CreateInstance@CUsbBusFilter@@SAJPEAUWDFDEVICE__@@EPEAXPEAPEAV1@@Z`
- size: `243`
- prototype: `__int64 __fastcall(struct WDFDEVICE__ *, unsigned __int8, void *, struct CUsbBusFilter **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140012010`

## callees

- `0x140001e28`
- `0x1400029e4`
- `0x140003acc`
- `0x140004f18`
- `0x140004f48`

## pseudocode

```c
__int64 __fastcall CUsbBusFilter::CreateInstance(
        struct WDFDEVICE__ *a1,
        char a2,
        _QWORD *a3,
        struct CUsbBusFilter **a4)
{
  int v6; // edi

  if ( a3 )
  {
    *a3 = 0;
    a3[1] = 0;
    a3[2] = 0;
    a3[3] = 0;
    a3[4] = 0;
    *((_BYTE *)a3 + 40) = 0;
    a3[6] = 0;
    *((_BYTE *)a3 + 60) = 0;
    v6 = CUsbBusFilter::Initialize((CUsbBusFilter *)a3, a1, a2);
    if ( v6 >= 0 )
    {
      v6 = 0;
      *a4 = (struct CUsbBusFilter *)a3;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids,
          (unsigned int)v6);
      CUsbBusFilter::~CUsbBusFilter((CUsbBusFilter *)a3);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids);
    return (unsigned int)-1073741801;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400029e4  mov     [rsp+arg_0], rbx
0x1400029e9  mov     [rsp+arg_8], rsi
0x1400029ee  push    rdi
0x1400029ef  sub     rsp, 20h
0x1400029f3  mov     rsi, r9
0x1400029f6  mov     rbx, r8
0x1400029f9  test    r8, r8
0x1400029fc  jz      loc_140002A91
0x140002a02  mov     qword ptr [r8], 0
0x140002a09  mov     qword ptr [r8+8], 0
0x140002a11  mov     qword ptr [r8+10h], 0
0x140002a19  mov     qword ptr [r8+18h], 0
0x140002a21  mov     qword ptr [r8+20h], 0
0x140002a29  mov     byte ptr [r8+28h], 0
0x140002a2e  mov     qword ptr [r8+30h], 0
0x140002a36  mov     byte ptr [r8+3Ch], 0
0x140002a3b  mov     r8b, dl; unsigned __int8
0x140002a3e  mov     rdx, rcx; struct WDFDEVICE__ *
0x140002a41  mov     rcx, rbx; this
0x140002a44  call    ?Initialize@CUsbBusFilter@@AEAAJPEAUWDFDEVICE__@@E@Z; CUsbBusFilter::Initialize(WDFDEVICE__ *,uchar)
0x140002a49  mov     edi, eax
0x140002a4b  test    eax, eax
0x140002a4d  jns     short loc_140002A8A
0x140002a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a56  lea     rax, WPP_GLOBAL_Control
0x140002a5d  cmp     rcx, rax
0x140002a60  jz      short loc_140002A80
0x140002a62  cmp     byte ptr [rcx+29h], 2
0x140002a66  jb      short loc_140002A80
0x140002a68  mov     rcx, [rcx+18h]
0x140002a6c  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140002a73  mov     edx, 0Bh
0x140002a78  mov     r9d, edi
0x140002a7b  call    WPP_SF_d
0x140002a80  mov     rcx, rbx; this
0x140002a83  call    ??1CUsbBusFilter@@QEAA@XZ; CUsbBusFilter::~CUsbBusFilter(void)
0x140002a88  jmp     short loc_140002AC4
0x140002a8a  xor     edi, edi
0x140002a8c  mov     [rsi], rbx
0x140002a8f  jmp     short loc_140002AC4
0x140002a91  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a98  lea     rax, WPP_GLOBAL_Control
0x140002a9f  cmp     rcx, rax
0x140002aa2  jz      short loc_140002ABF
0x140002aa4  cmp     byte ptr [rcx+29h], 2
0x140002aa8  jb      short loc_140002ABF
0x140002aaa  mov     rcx, [rcx+18h]
0x140002aae  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140002ab5  mov     edx, 0Ah
0x140002aba  call    WPP_SF_
0x140002abf  mov     edi, 0C0000017h
0x140002ac4  mov     rbx, [rsp+28h+arg_0]
0x140002ac9  mov     eax, edi
0x140002acb  mov     rsi, [rsp+28h+arg_8]
0x140002ad0  add     rsp, 20h
0x140002ad4  pop     rdi
0x140002ad5  retn
```
