# CreateImageHandle

- ea: `0x180011df8`
- end: `0x180012087`
- name: `CreateImageHandle`
- size: `655`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f7c4`
- `0x180013690`

## callees

- `0x180011df8`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180011efb`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180011f13`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180011f2a`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180011f42`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180011efb`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180011f13`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180011f2a`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180011f42`
- `KERNEL32!HeapFree` at `0x180012045`
- `KERNEL32!HeapFree` at `0x180012045`
- `KERNEL32!HeapAlloc` at `0x180011e3d`
- `KERNEL32!HeapAlloc` at `0x180011e3d`
- `KERNEL32!GetLastError` at `0x180011f63`
- `KERNEL32!GetLastError` at `0x180011f63`
- `KERNEL32!DeleteCriticalSection` at `0x180011fde`
- `KERNEL32!DeleteCriticalSection` at `0x180011ff5`
- `KERNEL32!DeleteCriticalSection` at `0x18001200d`
- `KERNEL32!DeleteCriticalSection` at `0x180012025`
- `KERNEL32!DeleteCriticalSection` at `0x180011fde`
- `KERNEL32!DeleteCriticalSection` at `0x180011ff5`
- `KERNEL32!DeleteCriticalSection` at `0x18001200d`
- `KERNEL32!DeleteCriticalSection` at `0x180012025`
- `KERNEL32!CloseHandle` at `0x180011fae`
- `KERNEL32!CloseHandle` at `0x180011fc6`
- `KERNEL32!CloseHandle` at `0x180011fae`
- `KERNEL32!CloseHandle` at `0x180011fc6`
- `KERNEL32!CreateEventW` at `0x180011e92`
- `KERNEL32!CreateEventW` at `0x180011eaf`
- `KERNEL32!CreateEventW` at `0x180011e92`
- `KERNEL32!CreateEventW` at `0x180011eaf`
- `KERNEL32!SetLastError` at `0x180012059`
- `KERNEL32!SetLastError` at `0x180012059`
- `KERNEL32!GetProcessHeap` at `0x180011e25`
- `KERNEL32!GetProcessHeap` at `0x180012031`
- `KERNEL32!GetProcessHeap` at `0x180011e25`
- `KERNEL32!GetProcessHeap` at `0x180012031`
- `RPCRT4!UuidCreate` at `0x180011edc`
- `RPCRT4!UuidCreate` at `0x180011edc`

## pseudocode

```c
char *__fastcall CreateImageHandle(__int64 a1, int a2)
{
  BOOL v4; // r12d
  BOOL v5; // ebp
  BOOL v6; // r14d
  BOOL v7; // r15d
  HANDLE ProcessHeap; // rax
  char *result; // rax
  void *v10; // rbx
  _DWORD *v11; // rax
  DWORD LastError; // edi
  HANDLE EventW; // rax
  BOOL v14; // eax
  void *v15; // rcx
  void *v16; // rcx
  HANDLE v17; // rax

  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  ProcessHeap = GetProcessHeap();
  result = (char *)HeapAlloc(ProcessHeap, 8u, 0x238u);
  v10 = result;
  if ( result )
  {
    memset_0(result + 4, 0, 0x234u);
    *(_DWORD *)v10 = -17960958;
    if ( a1 )
      *((_QWORD *)v10 + 1) = a1;
    v11 = (_DWORD *)*((_QWORD *)v10 + 8);
    if ( !v11 )
      v11 = v10;
    v11[8] = a2;
    LastError = 6;
    *((_QWORD *)v10 + 48) = CreateEventW(0, 0, 0, 0);
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)v10 + 49) = EventW;
    if ( !*((_QWORD *)v10 + 48) )
      goto LABEL_18;
    if ( !EventW )
      goto LABEL_18;
    LastError = UuidCreate((UUID *)v10 + 1);
    if ( LastError )
      goto LABEL_18;
    v4 = InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)v10 + 10, 0);
    v5 = InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)v10 + 11, 0);
    v6 = InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)v10 + 12, 0);
    v14 = InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)v10 + 13, 0);
    v7 = v14;
    if ( v4 )
    {
      if ( v5 && v6 && v14 )
        goto LABEL_16;
    }
    LastError = GetLastError();
    if ( !LastError )
      LastError = 31;
    if ( !LastError )
    {
LABEL_16:
      if ( a1 )
      {
        *((_QWORD *)v10 + 70) = *(_QWORD *)(a1 + 576);
        *(_QWORD *)(a1 + 576) = v10;
      }
    }
    else
    {
LABEL_18:
      v15 = (void *)*((_QWORD *)v10 + 48);
      if ( v15 )
        CloseHandle(v15);
      v16 = (void *)*((_QWORD *)v10 + 49);
      if ( v16 )
        CloseHandle(v16);
      if ( v4 )
        DeleteCriticalSection((LPCRITICAL_SECTION)v10 + 10);
      if ( v5 )
        DeleteCriticalSection((LPCRITICAL_SECTION)v10 + 11);
      if ( v6 )
        DeleteCriticalSection((LPCRITICAL_SECTION)v10 + 12);
      if ( v7 )
        DeleteCriticalSection((LPCRITICAL_SECTION)v10 + 13);
      v17 = GetProcessHeap();
      HeapFree(v17, 0, v10);
      v10 = 0;
      if ( LastError )
        SetLastError(LastError);
    }
    return (char *)v10;
  }
  return result;
}

```

## disassembly

```asm
0x180011df8  mov     rax, rsp
0x180011dfb  mov     [rax+8], rbx
0x180011dff  mov     [rax+10h], rbp
0x180011e03  mov     [rax+18h], rsi
0x180011e07  mov     [rax+20h], rdi
0x180011e0b  push    r12
0x180011e0d  push    r14
0x180011e0f  push    r15
0x180011e11  sub     rsp, 20h
0x180011e15  mov     edi, edx
0x180011e17  mov     rsi, rcx
0x180011e1a  xor     r12d, r12d
0x180011e1d  xor     ebp, ebp
0x180011e1f  xor     r14d, r14d
0x180011e22  xor     r15d, r15d
0x180011e25  call    cs:__imp_GetProcessHeap
0x180011e2c  nop     dword ptr [rax+rax+00h]
0x180011e31  lea     edx, [rbp+8]; dwFlags
0x180011e34  mov     r8d, 238h; dwBytes
0x180011e3a  mov     rcx, rax; hHeap
0x180011e3d  call    cs:__imp_HeapAlloc
0x180011e44  nop     dword ptr [rax+rax+00h]
0x180011e49  mov     rbx, rax
0x180011e4c  test    rax, rax
0x180011e4f  jz      loc_180012068
0x180011e55  lea     rcx, [rax+4]; void *
0x180011e59  xor     edx, edx; Val
0x180011e5b  mov     r8d, 234h; Size
0x180011e61  call    memset_0
0x180011e66  mov     dword ptr [rbx], 0FEEDF002h
0x180011e6c  test    rsi, rsi
0x180011e6f  jz      short loc_180011E75
0x180011e71  mov     [rbx+8], rsi
0x180011e75  mov     rax, [rbx+40h]
0x180011e79  test    rax, rax
0x180011e7c  cmovz   rax, rbx
0x180011e80  xor     r9d, r9d; lpName
0x180011e83  xor     r8d, r8d; bInitialState
0x180011e86  xor     edx, edx; bManualReset
0x180011e88  xor     ecx, ecx; lpEventAttributes
0x180011e8a  mov     [rax+20h], edi
0x180011e8d  mov     edi, 6
0x180011e92  call    cs:__imp_CreateEventW
0x180011e99  nop     dword ptr [rax+rax+00h]
0x180011e9e  xor     r9d, r9d; lpName
0x180011ea1  xor     r8d, r8d; bInitialState
0x180011ea4  xor     edx, edx; bManualReset
0x180011ea6  mov     [rbx+180h], rax
0x180011ead  xor     ecx, ecx; lpEventAttributes
0x180011eaf  call    cs:__imp_CreateEventW
0x180011eb6  nop     dword ptr [rax+rax+00h]
0x180011ebb  mov     [rbx+188h], rax
0x180011ec2  cmp     [rbx+180h], rbp
0x180011ec9  jz      loc_180011FA2
0x180011ecf  test    rax, rax
0x180011ed2  jz      loc_180011FA2
0x180011ed8  lea     rcx, [rbx+10h]; Uuid
0x180011edc  call    cs:__imp_UuidCreate
0x180011ee3  nop     dword ptr [rax+rax+00h]
0x180011ee8  mov     edi, eax
0x180011eea  test    eax, eax
0x180011eec  jnz     loc_180011FA2
0x180011ef2  lea     rcx, [rbx+190h]; lpCriticalSection
0x180011ef9  xor     edx, edx; dwSpinCount
0x180011efb  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180011f02  nop     dword ptr [rax+rax+00h]
0x180011f07  lea     rcx, [rbx+1B8h]; lpCriticalSection
0x180011f0e  xor     edx, edx; dwSpinCount
0x180011f10  mov     r12d, eax
0x180011f13  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180011f1a  nop     dword ptr [rax+rax+00h]
0x180011f1f  lea     rcx, [rbx+1E0h]; lpCriticalSection
0x180011f26  xor     edx, edx; dwSpinCount
0x180011f28  mov     ebp, eax
0x180011f2a  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180011f31  nop     dword ptr [rax+rax+00h]
0x180011f36  lea     rcx, [rbx+208h]; lpCriticalSection
0x180011f3d  xor     edx, edx; dwSpinCount
0x180011f3f  mov     r14d, eax
0x180011f42  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180011f49  nop     dword ptr [rax+rax+00h]
0x180011f4e  mov     r15d, eax
0x180011f51  test    r12d, r12d
0x180011f54  jz      short loc_180011F63
0x180011f56  test    ebp, ebp
0x180011f58  jz      short loc_180011F63
0x180011f5a  test    r14d, r14d
0x180011f5d  jz      short loc_180011F63
0x180011f5f  test    eax, eax
0x180011f61  jnz     short loc_180011F7F
0x180011f63  call    cs:__imp_GetLastError
0x180011f6a  nop     dword ptr [rax+rax+00h]
0x180011f6f  mov     edi, eax
0x180011f71  mov     eax, 1Fh
0x180011f76  test    edi, edi
0x180011f78  cmovz   edi, eax
0x180011f7b  test    edi, edi
0x180011f7d  jnz     short loc_180011FA2
0x180011f7f  test    rsi, rsi
0x180011f82  jz      loc_180012065
0x180011f88  mov     rax, [rsi+240h]
0x180011f8f  mov     [rbx+230h], rax
0x180011f96  mov     [rsi+240h], rbx
0x180011f9d  jmp     loc_180012065
0x180011fa2  mov     rcx, [rbx+180h]; hObject
0x180011fa9  test    rcx, rcx
0x180011fac  jz      short loc_180011FBA
0x180011fae  call    cs:__imp_CloseHandle
0x180011fb5  nop     dword ptr [rax+rax+00h]
0x180011fba  mov     rcx, [rbx+188h]; hObject
0x180011fc1  test    rcx, rcx
0x180011fc4  jz      short loc_180011FD2
0x180011fc6  call    cs:__imp_CloseHandle
0x180011fcd  nop     dword ptr [rax+rax+00h]
0x180011fd2  test    r12d, r12d
0x180011fd5  jz      short loc_180011FEA
0x180011fd7  lea     rcx, [rbx+190h]; lpCriticalSection
0x180011fde  call    cs:__imp_DeleteCriticalSection
0x180011fe5  nop     dword ptr [rax+rax+00h]
0x180011fea  test    ebp, ebp
0x180011fec  jz      short loc_180012001
0x180011fee  lea     rcx, [rbx+1B8h]; lpCriticalSection
0x180011ff5  call    cs:__imp_DeleteCriticalSection
0x180011ffc  nop     dword ptr [rax+rax+00h]
0x180012001  test    r14d, r14d
0x180012004  jz      short loc_180012019
0x180012006  lea     rcx, [rbx+1E0h]; lpCriticalSection
0x18001200d  call    cs:__imp_DeleteCriticalSection
0x180012014  nop     dword ptr [rax+rax+00h]
0x180012019  test    r15d, r15d
0x18001201c  jz      short loc_180012031
0x18001201e  lea     rcx, [rbx+208h]; lpCriticalSection
0x180012025  call    cs:__imp_DeleteCriticalSection
0x18001202c  nop     dword ptr [rax+rax+00h]
0x180012031  call    cs:__imp_GetProcessHeap
0x180012038  nop     dword ptr [rax+rax+00h]
0x18001203d  mov     r8, rbx; lpMem
0x180012040  xor     edx, edx; dwFlags
0x180012042  mov     rcx, rax; hHeap
0x180012045  call    cs:__imp_HeapFree
0x18001204c  nop     dword ptr [rax+rax+00h]
0x180012051  xor     ebx, ebx
0x180012053  test    edi, edi
0x180012055  jz      short loc_180012065
0x180012057  mov     ecx, edi; dwErrCode
0x180012059  call    cs:__imp_SetLastError
0x180012060  nop     dword ptr [rax+rax+00h]
0x180012065  mov     rax, rbx
0x180012068  mov     rbx, [rsp+38h+arg_0]
0x18001206d  mov     rbp, [rsp+38h+arg_8]
0x180012072  mov     rsi, [rsp+38h+arg_10]
0x180012077  mov     rdi, [rsp+38h+arg_18]
0x18001207c  add     rsp, 20h
0x180012080  pop     r15
0x180012082  pop     r14
0x180012084  pop     r12
0x180012086  retn
```
