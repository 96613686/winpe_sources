# CPXWizardMutexLock::ReleaseLock(void)

- ea: `0x180011ecc`
- end: `0x180011fa4`
- name: `?ReleaseLock@CPXWizardMutexLock@@QEAAJXZ`
- size: `216`
- prototype: `__int64 __fastcall(CPXWizardMutexLock *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d548`
- `0x180011710`
- `0x180011820`
- `0x180011a10`

## callees

- `0x180007820`
- `0x180011ecc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011f1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011f1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011f26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011f26`

## pseudocode

```c
__int64 __fastcall CPXWizardMutexLock::ReleaseLock(CPXWizardMutexLock *this)
{
  unsigned int v1; // ebx
  PVOID *v3; // rcx
  USHORT v4; // dx
  void *v5; // rcx

  v1 = *(_DWORD *)this;
  if ( *(int *)this < 0 )
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v4 = 24;
LABEL_14:
      WPP_SF_D((TRACEHANDLE)v3[2], v4, (const GUID *)WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, v1);
      return v1;
    }
    return v1;
  }
  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 )
  {
    ReleaseMutex(v5);
    CloseHandle(*((HANDLE *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  else
  {
    v1 = -2147024891;
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v1;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_11;
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0x19u,
      (const GUID *)WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids,
      -2147024891);
  }
  v3 = (PVOID *)WPP_GLOBAL_Control;
LABEL_11:
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x10) != 0 )
  {
    v4 = 26;
    goto LABEL_14;
  }
  return v1;
}

```

## disassembly

```asm
0x180011ecc  mov     [rsp+arg_0], rbx
0x180011ed1  mov     [rsp+arg_8], rsi
0x180011ed6  push    rdi
0x180011ed7  sub     rsp, 20h
0x180011edb  mov     ebx, [rcx]
0x180011edd  mov     rsi, rcx
0x180011ee0  test    ebx, ebx
0x180011ee2  jns     short loc_180011F0C
0x180011ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011eeb  lea     rdi, WPP_GLOBAL_Control
0x180011ef2  cmp     rcx, rdi
0x180011ef5  jz      loc_180011F92
0x180011efb  test    byte ptr [rcx+1Ch], 4
0x180011eff  jz      loc_180011F92
0x180011f05  mov     edx, 18h
0x180011f0a  jmp     short loc_180011F7F
0x180011f0c  mov     rcx, [rcx+8]; hMutex
0x180011f10  lea     rdi, WPP_GLOBAL_Control
0x180011f17  test    rcx, rcx
0x180011f1a  jz      short loc_180011F36
0x180011f1c  call    cs:__imp_ReleaseMutex
0x180011f22  mov     rcx, [rsi+8]; hObject
0x180011f26  call    cs:__imp_CloseHandle
0x180011f2c  mov     qword ptr [rsi+8], 0
0x180011f34  jmp     short loc_180011F68
0x180011f36  mov     ebx, 80070005h
0x180011f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f42  cmp     rcx, rdi
0x180011f45  jz      short loc_180011F92
0x180011f47  test    byte ptr [rcx+1Ch], 10h
0x180011f4b  jz      short loc_180011F6F
0x180011f4d  mov     rcx, [rcx+10h]
0x180011f51  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x180011f58  mov     edx, 19h
0x180011f5d  mov     r9d, 80070005h
0x180011f63  call    WPP_SF_D
0x180011f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f6f  cmp     rcx, rdi
0x180011f72  jz      short loc_180011F92
0x180011f74  test    byte ptr [rcx+1Ch], 10h
0x180011f78  jz      short loc_180011F92
0x180011f7a  mov     edx, 1Ah
0x180011f7f  mov     rcx, [rcx+10h]
0x180011f83  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x180011f8a  mov     r9d, ebx
0x180011f8d  call    WPP_SF_D
0x180011f92  mov     rsi, [rsp+28h+arg_8]
0x180011f97  mov     eax, ebx
0x180011f99  mov     rbx, [rsp+28h+arg_0]
0x180011f9e  add     rsp, 20h
0x180011fa2  pop     rdi
0x180011fa3  retn
```
