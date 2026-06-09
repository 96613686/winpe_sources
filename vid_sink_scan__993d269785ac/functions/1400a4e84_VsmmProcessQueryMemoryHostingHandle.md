# VsmmProcessQueryMemoryHostingHandle

- ea: `0x1400a4e84`
- end: `0x1400a5050`
- name: `VsmmProcessQueryMemoryHostingHandle`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14008ca04`

## callees

- `0x14002f524`
- `0x140034554`
- `0x140034584`
- `0x140038630`
- `0x1400a4e84`

## import_xrefs

- `ntoskrnl!PsProcessType` at `0x1400a4f8f`
- `ntoskrnl!ObOpenObjectByPointerWithTag` at `0x1400a4fd4`
- `ntoskrnl!ObOpenObjectByPointerWithTag` at `0x1400a4fd4`
- `ntoskrnl!ExGetPreviousMode` at `0x1400a4fa2`
- `ntoskrnl!ExGetPreviousMode` at `0x1400a4fa2`
- `ntoskrnl!NtClose` at `0x1400a5014`
- `ntoskrnl!NtClose` at `0x1400a5014`

## pseudocode

```c
__int64 __fastcall VsmmProcessQueryMemoryHostingHandle(
        __int64 a1,
        ACCESS_MASK *a2,
        int a3,
        HANDLE *a4,
        int a5,
        _DWORD *a6)
{
  NTSTATUS v9; // ebx
  __int64 v10; // rbp
  ACCESS_MASK v11; // edi
  void *v12; // rsi
  KPROCESSOR_MODE AccessMode; // al
  HANDLE Handle; // [rsp+68h] [rbp+10h] BYREF

  Handle = 0;
  if ( a2 )
  {
    if ( a3 == 4 )
    {
      if ( a4 )
      {
        if ( a5 == 8 )
        {
          v10 = a1 + 10256;
          VidObjectLockAcquireShared(a1 + 10256);
          if ( *(_QWORD *)(a1 + 10328) )
          {
            v11 = *a2;
            v12 = *(void **)(a1 + 10328);
            AccessMode = ExGetPreviousMode();
            v9 = ObOpenObjectByPointerWithTag(
                   v12,
                   0,
                   0,
                   v11,
                   (POBJECT_TYPE)PsProcessType,
                   AccessMode,
                   0x6D4D6456u,
                   &Handle);
            VidObjectLockRelease(v10);
            if ( v9 >= 0 )
            {
              v9 = 0;
              *a4 = Handle;
              *a6 = 8;
              return (unsigned int)v9;
            }
            VidTraceErrorStatusInternal0(
              "VsmmProcessQueryMemoryHostingHandle",
              "onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c",
              496);
          }
          else
          {
            v9 = -1073741811;
            VidTraceErrorInternal0(
              "VsmmProcessQueryMemoryHostingHandle",
              "onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c",
              477);
            VidObjectLockRelease(v10);
          }
        }
        else
        {
          v9 = -1073741811;
          VidTraceErrorInternal0(
            "VsmmProcessQueryMemoryHostingHandle",
            "onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c",
            463);
        }
      }
      else
      {
        v9 = -1073741811;
        VidTraceErrorInternal0("VsmmProcessQueryMemoryHostingHandle", "onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c", 456);
      }
    }
    else
    {
      v9 = -1073741811;
      VidTraceErrorInternal0("VsmmProcessQueryMemoryHostingHandle", "onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c", 449);
    }
  }
  else
  {
    v9 = -1073741811;
    VidTraceErrorInternal0("VsmmProcessQueryMemoryHostingHandle", "onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c", 438);
  }
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400a4e84  mov     [rsp+arg_0], rbx
0x1400a4e89  mov     [rsp+arg_10], rbp
0x1400a4e8e  push    rsi
0x1400a4e8f  push    rdi
0x1400a4e90  push    r14
0x1400a4e92  sub     rsp, 40h
0x1400a4e96  mov     [rsp+58h+arg_8], 0
0x1400a4e9f  mov     r14, r9
0x1400a4ea2  mov     rdi, rdx
0x1400a4ea5  mov     rsi, rcx
0x1400a4ea8  test    rdx, rdx
0x1400a4eab  jnz     short loc_1400A4ED0
0x1400a4ead  mov     ebx, 0C000000Dh
0x1400a4eb2  mov     r8d, 1B6h
0x1400a4eb8  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a4ebf  lea     rcx, aVsmmprocessque; "VsmmProcessQueryMemoryHostingHandle"
0x1400a4ec6  call    VidTraceErrorInternal0
0x1400a4ecb  jmp     loc_1400A500A
0x1400a4ed0  cmp     r8d, 4
0x1400a4ed4  jz      short loc_1400A4EF9
0x1400a4ed6  mov     ebx, 0C000000Dh
0x1400a4edb  mov     r8d, 1C1h
0x1400a4ee1  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a4ee8  lea     rcx, aVsmmprocessque; "VsmmProcessQueryMemoryHostingHandle"
0x1400a4eef  call    VidTraceErrorInternal0
0x1400a4ef4  jmp     loc_1400A500A
0x1400a4ef9  test    r14, r14
0x1400a4efc  jnz     short loc_1400A4F21
0x1400a4efe  mov     ebx, 0C000000Dh
0x1400a4f03  mov     r8d, 1C8h
0x1400a4f09  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a4f10  lea     rcx, aVsmmprocessque; "VsmmProcessQueryMemoryHostingHandle"
0x1400a4f17  call    VidTraceErrorInternal0
0x1400a4f1c  jmp     loc_1400A500A
0x1400a4f21  cmp     [rsp+58h+arg_20], 8
0x1400a4f29  jz      short loc_1400A4F4E
0x1400a4f2b  mov     ebx, 0C000000Dh
0x1400a4f30  mov     r8d, 1CFh
0x1400a4f36  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a4f3d  lea     rcx, aVsmmprocessque; "VsmmProcessQueryMemoryHostingHandle"
0x1400a4f44  call    VidTraceErrorInternal0
0x1400a4f49  jmp     loc_1400A500A
0x1400a4f4e  lea     rbp, [rcx+2810h]
0x1400a4f55  mov     rcx, rbp
0x1400a4f58  call    VidObjectLockAcquireShared
0x1400a4f5d  cmp     qword ptr [rsi+2858h], 0
0x1400a4f65  jnz     short loc_1400A4F8F
0x1400a4f67  mov     ebx, 0C000000Dh
0x1400a4f6c  mov     r8d, 1DDh
0x1400a4f72  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a4f79  lea     rcx, aVsmmprocessque; "VsmmProcessQueryMemoryHostingHandle"
0x1400a4f80  call    VidTraceErrorInternal0
0x1400a4f85  mov     rcx, rbp
0x1400a4f88  call    VidObjectLockRelease
0x1400a4f8d  jmp     short loc_1400A500A
0x1400a4f8f  mov     rax, cs:__imp_PsProcessType
0x1400a4f96  mov     edi, [rdi]
0x1400a4f98  mov     rsi, [rsi+2858h]
0x1400a4f9f  mov     rbx, [rax]
0x1400a4fa2  call    cs:__imp_ExGetPreviousMode
0x1400a4fa9  nop     dword ptr [rax+rax+00h]
0x1400a4fae  lea     rcx, [rsp+58h+arg_8]
0x1400a4fb3  mov     r9d, edi; DesiredAccess
0x1400a4fb6  mov     [rsp+58h+Handle], rcx; Handle
0x1400a4fbb  xor     r8d, r8d; PassedAccessState
0x1400a4fbe  mov     [rsp+58h+Tag], 6D4D6456h; Tag
0x1400a4fc6  xor     edx, edx; HandleAttributes
0x1400a4fc8  mov     [rsp+58h+AccessMode], al; AccessMode
0x1400a4fcc  mov     rcx, rsi; Object
0x1400a4fcf  mov     [rsp+58h+ObjectType], rbx; ObjectType
0x1400a4fd4  call    cs:__imp_ObOpenObjectByPointerWithTag
0x1400a4fdb  nop     dword ptr [rax+rax+00h]
0x1400a4fe0  mov     rcx, rbp
0x1400a4fe3  mov     ebx, eax
0x1400a4fe5  call    VidObjectLockRelease
0x1400a4fea  test    ebx, ebx
0x1400a4fec  jns     short loc_1400A5022
0x1400a4fee  mov     r9d, ebx
0x1400a4ff1  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a4ff8  mov     r8d, 1F0h
0x1400a4ffe  lea     rcx, aVsmmprocessque; "VsmmProcessQueryMemoryHostingHandle"
0x1400a5005  call    VidTraceErrorStatusInternal0
0x1400a500a  mov     rcx, [rsp+58h+arg_8]; Handle
0x1400a500f  test    rcx, rcx
0x1400a5012  jz      short loc_1400A503A
0x1400a5014  call    cs:__imp_NtClose
0x1400a501b  nop     dword ptr [rax+rax+00h]
0x1400a5020  jmp     short loc_1400A503A
0x1400a5022  mov     rax, [rsp+58h+arg_8]
0x1400a5027  xor     ebx, ebx
0x1400a5029  mov     [r14], rax
0x1400a502c  mov     rax, [rsp+58h+arg_28]
0x1400a5034  mov     dword ptr [rax], 8
0x1400a503a  mov     rbp, [rsp+58h+arg_10]
0x1400a503f  mov     eax, ebx
0x1400a5041  mov     rbx, [rsp+58h+arg_0]
0x1400a5046  add     rsp, 40h
0x1400a504a  pop     r14
0x1400a504c  pop     rdi
0x1400a504d  pop     rsi
0x1400a504e  retn
```
