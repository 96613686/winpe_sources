# RfspThreadPoolNodeCreateThread

- ea: `0x14009207c`
- end: `0x140092143`
- name: `RfspThreadPoolNodeCreateThread`
- size: `199`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140091e6c`

## callees

- `0x14009207c`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14009212e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14009212e`
- `ntoskrnl!PsThreadType` at `0x14009210b`
- `ntoskrnl!IoCreateSystemThread` at `0x1400920d1`
- `ntoskrnl!IoCreateSystemThread` at `0x1400920d1`

## pseudocode

```c
__int64 __fastcall RfspThreadPoolNodeCreateThread(__int64 a1, __int64 a2, __int64 a3, HANDLE *a4, PVOID *Object)
{
  _QWORD *v5; // rcx
  __int64 result; // rax
  _QWORD v8[4]; // [rsp+40h] [rbp-38h] BYREF
  __int128 v9; // [rsp+60h] [rbp-18h]

  v5 = *(_QWORD **)(a1 + 216);
  v8[0] = 48;
  v8[3] = 512;
  v8[1] = 0;
  v8[2] = 0;
  v9 = 0;
  result = ((__int64 (__fastcall *)(_QWORD, HANDLE *, __int64, _QWORD *, _QWORD, _QWORD, __int64, __int64))IoCreateSystemThread)(
             *v5,
             a4,
             0x1FFFFF,
             v8,
             0,
             0,
             a2,
             a3);
  if ( (int)result >= 0 )
  {
    if ( Object )
      ObReferenceObjectByHandle(*a4, 0x1FFFFFu, (POBJECT_TYPE)PsThreadType, 0, Object, 0);
    return 0;
  }
  else
  {
    *a4 = 0;
    if ( Object )
      *Object = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14009207c  mov     r11, rsp
0x14009207f  push    rbx
0x140092080  sub     rsp, 70h
0x140092084  mov     rcx, [rcx+0D8h]
0x14009208b  xor     eax, eax
0x14009208d  mov     [r11-40h], r8
0x140092091  mov     rbx, r9
0x140092094  mov     [r11-48h], rdx
0x140092098  lea     r9, [r11-38h]
0x14009209c  mov     qword ptr [r11-38h], 30h ; '0'
0x1400920a4  xorps   xmm0, xmm0
0x1400920a7  mov     qword ptr [r11-20h], 200h
0x1400920af  mov     r8d, 1FFFFFh
0x1400920b5  mov     [r11-30h], rax
0x1400920b9  mov     rdx, rbx
0x1400920bc  mov     [r11-28h], rax
0x1400920c0  movdqu  [rsp+78h+var_18], xmm0
0x1400920c6  mov     rcx, [rcx]
0x1400920c9  mov     [r11-50h], rax
0x1400920cd  mov     [r11-58h], rax
0x1400920d1  call    cs:__imp_IoCreateSystemThread
0x1400920d8  nop     dword ptr [rax+rax+00h]
0x1400920dd  test    eax, eax
0x1400920df  jns     short loc_1400920FE
0x1400920e1  mov     rcx, [rsp+78h+arg_20]
0x1400920e9  mov     qword ptr [rbx], 0
0x1400920f0  test    rcx, rcx
0x1400920f3  jz      short loc_14009213C
0x1400920f5  mov     qword ptr [rcx], 0
0x1400920fc  jmp     short loc_14009213C
0x1400920fe  mov     rax, [rsp+78h+arg_20]
0x140092106  test    rax, rax
0x140092109  jz      short loc_14009213A
0x14009210b  mov     r8, cs:__imp_PsThreadType
0x140092112  xor     r9d, r9d; AccessMode
0x140092115  mov     rcx, [rbx]; Handle
0x140092118  mov     edx, 1FFFFFh; DesiredAccess
0x14009211d  mov     [rsp+78h+HandleInformation], 0; HandleInformation
0x140092126  mov     [rsp+78h+Object], rax; Object
0x14009212b  mov     r8, [r8]; ObjectType
0x14009212e  call    cs:__imp_ObReferenceObjectByHandle
0x140092135  nop     dword ptr [rax+rax+00h]
0x14009213a  xor     eax, eax
0x14009213c  add     rsp, 70h
0x140092140  pop     rbx
0x140092141  retn
```
