# RfspThreadPoolNodeCreateThread

- ea: `0x1400920cc`
- end: `0x140092193`
- name: `RfspThreadPoolNodeCreateThread`
- size: `199`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140091ebc`

## callees

- `0x1400920cc`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14009217e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14009217e`
- `ntoskrnl!PsThreadType` at `0x14009215b`
- `ntoskrnl!IoCreateSystemThread` at `0x140092121`
- `ntoskrnl!IoCreateSystemThread` at `0x140092121`

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
0x1400920cc  mov     r11, rsp
0x1400920cf  push    rbx
0x1400920d0  sub     rsp, 70h
0x1400920d4  mov     rcx, [rcx+0D8h]
0x1400920db  xor     eax, eax
0x1400920dd  mov     [r11-40h], r8
0x1400920e1  mov     rbx, r9
0x1400920e4  mov     [r11-48h], rdx
0x1400920e8  lea     r9, [r11-38h]
0x1400920ec  mov     qword ptr [r11-38h], 30h ; '0'
0x1400920f4  xorps   xmm0, xmm0
0x1400920f7  mov     qword ptr [r11-20h], 200h
0x1400920ff  mov     r8d, 1FFFFFh
0x140092105  mov     [r11-30h], rax
0x140092109  mov     rdx, rbx
0x14009210c  mov     [r11-28h], rax
0x140092110  movdqu  [rsp+78h+var_18], xmm0
0x140092116  mov     rcx, [rcx]
0x140092119  mov     [r11-50h], rax
0x14009211d  mov     [r11-58h], rax
0x140092121  call    cs:__imp_IoCreateSystemThread
0x140092128  nop     dword ptr [rax+rax+00h]
0x14009212d  test    eax, eax
0x14009212f  jns     short loc_14009214E
0x140092131  mov     rcx, [rsp+78h+arg_20]
0x140092139  mov     qword ptr [rbx], 0
0x140092140  test    rcx, rcx
0x140092143  jz      short loc_14009218C
0x140092145  mov     qword ptr [rcx], 0
0x14009214c  jmp     short loc_14009218C
0x14009214e  mov     rax, [rsp+78h+arg_20]
0x140092156  test    rax, rax
0x140092159  jz      short loc_14009218A
0x14009215b  mov     r8, cs:__imp_PsThreadType
0x140092162  xor     r9d, r9d; AccessMode
0x140092165  mov     rcx, [rbx]; Handle
0x140092168  mov     edx, 1FFFFFh; DesiredAccess
0x14009216d  mov     [rsp+78h+HandleInformation], 0; HandleInformation
0x140092176  mov     [rsp+78h+Object], rax; Object
0x14009217b  mov     r8, [r8]; ObjectType
0x14009217e  call    cs:__imp_ObReferenceObjectByHandle
0x140092185  nop     dword ptr [rax+rax+00h]
0x14009218a  xor     eax, eax
0x14009218c  add     rsp, 70h
0x140092190  pop     rbx
0x140092191  retn
```
