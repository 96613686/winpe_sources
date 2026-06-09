# CPVRWriteBufferStreamWriter::CreateUniqueMutex_(_SECURITY_ATTRIBUTES *,_GUID *,void * *)

- ea: `0x180079128`
- end: `0x1800791d4`
- name: `?CreateUniqueMutex_@CPVRWriteBufferStreamWriter@@AEAAKPEAU_SECURITY_ATTRIBUTES@@PEAU_GUID@@PEAPEAX@Z`
- size: `172`
- prototype: `unsigned int(CPVRWriteBufferStreamWriter *__hidden this, struct _SECURITY_ATTRIBUTES *, struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180079f90`

## callees

- `0x180001c00`
- `0x180079128`
- `0x1800791dc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18007919a`
- `KERNEL32!CloseHandle` at `0x18007919a`
- `KERNEL32!GetLastError` at `0x180079184`
- `KERNEL32!GetLastError` at `0x1800791a9`
- `KERNEL32!GetLastError` at `0x180079184`
- `KERNEL32!GetLastError` at `0x1800791a9`
- `KERNEL32!CreateMutexW` at `0x180079176`
- `KERNEL32!CreateMutexW` at `0x180079176`

## pseudocode

```c
__int64 __fastcall CPVRWriteBufferStreamWriter::CreateUniqueMutex_(
        CPVRWriteBufferStreamWriter *this,
        struct _SECURITY_ATTRIBUTES *a2,
        struct _GUID *a3,
        void **a4)
{
  DWORD LastError; // ebx
  HANDLE MutexW; // rax
  WCHAR Name[264]; // [rsp+20h] [rbp-228h] BYREF

  *a4 = 0;
  if ( (int)CreateWriteCacheLockName(a3, a2, a3, Name) >= 0 )
  {
    MutexW = CreateMutexW(a2, 0, Name);
    *a4 = MutexW;
    if ( MutexW )
    {
      LastError = GetLastError();
      if ( LastError == 183 )
      {
        CloseHandle(*a4);
        *a4 = 0;
      }
      else
      {
        return 0;
      }
    }
    else
    {
      return GetLastError();
    }
  }
  else
  {
    return 31;
  }
  return LastError;
}

```

## disassembly

```asm
0x180079128  mov     [rsp+arg_0], rbx
0x18007912d  push    rdi
0x18007912e  sub     rsp, 240h
0x180079135  mov     rax, cs:__security_cookie
0x18007913c  xor     rax, rsp
0x18007913f  mov     [rsp+248h+var_18], rax
0x180079147  mov     rdi, r9
0x18007914a  mov     qword ptr [r9], 0
0x180079151  lea     r9, [rsp+248h+Name]
0x180079156  mov     rcx, r8
0x180079159  mov     rbx, rdx
0x18007915c  call    CreateWriteCacheLockName
0x180079161  test    eax, eax
0x180079163  jns     short loc_18007916C
0x180079165  mov     ebx, 1Fh
0x18007916a  jmp     short loc_1800791B1
0x18007916c  lea     r8, [rsp+248h+Name]; lpName
0x180079171  xor     edx, edx; bInitialOwner
0x180079173  mov     rcx, rbx; lpMutexAttributes
0x180079176  call    cs:__imp_CreateMutexW
0x18007917c  mov     [rdi], rax
0x18007917f  test    rax, rax
0x180079182  jz      short loc_1800791A9
0x180079184  call    cs:__imp_GetLastError
0x18007918a  mov     ebx, eax
0x18007918c  cmp     eax, 0B7h
0x180079191  jz      short loc_180079197
0x180079193  xor     ebx, ebx
0x180079195  jmp     short loc_1800791B1
0x180079197  mov     rcx, [rdi]; hObject
0x18007919a  call    cs:__imp_CloseHandle
0x1800791a0  mov     qword ptr [rdi], 0
0x1800791a7  jmp     short loc_1800791B1
0x1800791a9  call    cs:__imp_GetLastError
0x1800791af  mov     ebx, eax
0x1800791b1  mov     eax, ebx
0x1800791b3  mov     rcx, [rsp+248h+var_18]
0x1800791bb  xor     rcx, rsp; StackCookie
0x1800791be  call    __security_check_cookie
0x1800791c3  mov     rbx, [rsp+248h+arg_0]
0x1800791cb  add     rsp, 240h
0x1800791d2  pop     rdi
0x1800791d3  retn
```
