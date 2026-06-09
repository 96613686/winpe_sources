# FLTI_GetCurrent(AutoPtr<FileLogThreadInfo> *)

- ea: `0x18004eb38`
- end: `0x18004ebe8`
- name: `?FLTI_GetCurrent@@YAJPEAV?$AutoPtr@UFileLogThreadInfo@@@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180037164`
- `0x18004e894`
- `0x18004ea9c`
- `0x18004ebf0`
- `0x18004ec60`

## callees

- `0x180038c50`
- `0x18004e57c`
- `0x18004eb38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004eb4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004eb4a`
- `ntdll!RtlReleaseResource` at `0x18004ebc9`
- `ntdll!RtlReleaseResource` at `0x18004ebc9`
- `ntdll!RtlAcquireResourceShared` at `0x18004eb6c`
- `ntdll!RtlAcquireResourceShared` at `0x18004eb6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall FLTI_GetCurrent(void **a1)
{
  DWORD CurrentThreadId; // esi
  volatile signed __int32 ***v3; // rdi
  int v4; // ebx
  volatile signed __int32 **i; // rdx

  CurrentThreadId = GetCurrentThreadId();
  v3 = (volatile signed __int32 ***)*((_QWORD *)_pflstate + 9);
  if ( RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 216), 1u) )
  {
    for ( i = *v3; i != v3[1]; ++i )
    {
      if ( *(_DWORD *)(*((_QWORD *)*i + 1) + 8LL) == CurrentThreadId )
      {
        AutoPtr<FileLogThreadInfo>::operator=(a1, i);
        goto LABEL_9;
      }
    }
    v4 = FLTI_AddNew(a1);
    if ( v4 < 0 )
      goto LABEL_10;
LABEL_9:
    v4 = 0;
LABEL_10:
    RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 216));
  }
  else
  {
    return (unsigned int)-2147023537;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004eb38  mov     [rsp+arg_0], rbx
0x18004eb3d  mov     [rsp+arg_8], rsi
0x18004eb42  push    rdi
0x18004eb43  sub     rsp, 20h
0x18004eb47  mov     rbx, rcx
0x18004eb4a  call    cs:__imp_GetCurrentThreadId
0x18004eb51  nop     dword ptr [rax+rax+00h]
0x18004eb56  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18004eb5d  mov     dl, 1; Wait
0x18004eb5f  mov     esi, eax
0x18004eb61  mov     rdi, [rcx+48h]
0x18004eb65  add     rcx, 0D8h; Resource
0x18004eb6c  call    cs:__imp_RtlAcquireResourceShared
0x18004eb73  nop     dword ptr [rax+rax+00h]
0x18004eb78  test    al, al
0x18004eb7a  jnz     short loc_18004EB83
0x18004eb7c  mov     ebx, 8007054Fh
0x18004eb81  jmp     short loc_18004EBD5
0x18004eb83  mov     rdx, [rdi]
0x18004eb86  mov     r8, [rdi+8]
0x18004eb8a  cmp     rdx, r8
0x18004eb8d  jz      short loc_18004EBAB
0x18004eb8f  mov     rax, [rdx]
0x18004eb92  mov     rcx, [rax+8]
0x18004eb96  cmp     [rcx+8], esi
0x18004eb99  jz      short loc_18004EBA1
0x18004eb9b  add     rdx, 8
0x18004eb9f  jmp     short loc_18004EB8A
0x18004eba1  mov     rcx, rbx
0x18004eba4  call    ??4?$AutoPtr@UFileLogThreadInfo@@@@QEAAAEAV0@AEBV0@@Z; AutoPtr<FileLogThreadInfo>::operator=(AutoPtr<FileLogThreadInfo> const &)
0x18004eba9  jmp     short loc_18004EBB9
0x18004ebab  mov     rcx, rbx
0x18004ebae  call    ?FLTI_AddNew@@YAJPEAV?$AutoPtr@UFileLogThreadInfo@@@@@Z; FLTI_AddNew(AutoPtr<FileLogThreadInfo> *)
0x18004ebb3  mov     ebx, eax
0x18004ebb5  test    eax, eax
0x18004ebb7  js      short loc_18004EBBB
0x18004ebb9  xor     ebx, ebx
0x18004ebbb  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18004ebc2  add     rcx, 0D8h; Resource
0x18004ebc9  call    cs:__imp_RtlReleaseResource
0x18004ebd0  nop     dword ptr [rax+rax+00h]
0x18004ebd5  mov     rsi, [rsp+28h+arg_8]
0x18004ebda  mov     eax, ebx
0x18004ebdc  mov     rbx, [rsp+28h+arg_0]
0x18004ebe1  add     rsp, 20h
0x18004ebe5  pop     rdi
0x18004ebe6  retn
```
