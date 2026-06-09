# SetScheduleValues(ISyncSchedule *,_TASK_TRIGGER *,ulong)

- ea: `0x18000d7e4`
- end: `0x18000d904`
- name: `?SetScheduleValues@@YAJPEAUISyncSchedule@@PEAU_TASK_TRIGGER@@K@Z`
- size: `288`
- prototype: `int(struct ISyncSchedule *, struct _TASK_TRIGGER *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000b3fc`

## callees

- `0x18000ba94`
- `0x18000d7e4`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `WININET!InternetGetConnectedStateExW` at `0x18000d880`
- `WININET!InternetGetConnectedStateExW` at `0x18000d880`

## pseudocode

```c
__int64 __fastcall SetScheduleValues(struct ISyncSchedule *a1, struct _TASK_TRIGGER *a2, unsigned int a3)
{
  __int64 v3; // rax
  int v7; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-248h] BYREF
  __int64 v10; // [rsp+28h] [rbp-240h] BYREF
  WCHAR szConnectionName[264]; // [rsp+30h] [rbp-238h] BYREF

  v3 = *(_QWORD *)a1;
  v10 = 0;
  v7 = (*(__int64 (__fastcall **)(struct ISyncSchedule *, __int64 *))(v3 + 96))(a1, &v10);
  if ( v7 >= 0 )
  {
    FixupRandomTrigger(a2);
    v7 = (*(__int64 (__fastcall **)(__int64, struct _TASK_TRIGGER *))(*(_QWORD *)v10 + 24LL))(v10, a2);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v7 >= 0 )
    {
      dwFlags = 0;
      InternetGetConnectedStateExW(&dwFlags, szConnectionName, 0x104u, 0);
      v7 = (*(__int64 (__fastcall **)(struct ISyncSchedule *, unsigned __int64))(*(_QWORD *)a1 + 48LL))(
             a1,
             (unsigned __int64)szConnectionName & -(__int64)((dwFlags & 1) != 0));
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(struct ISyncSchedule *, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, a3);
        if ( v7 >= 0 )
          return (unsigned int)(*(__int64 (__fastcall **)(struct ISyncSchedule *))(*(_QWORD *)a1 + 160LL))(a1);
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d7e4  mov     [rsp+arg_18], rbx
0x18000d7e9  push    rbp
0x18000d7ea  push    rsi
0x18000d7eb  push    rdi
0x18000d7ec  sub     rsp, 250h
0x18000d7f3  mov     rax, cs:__security_cookie
0x18000d7fa  xor     rax, rsp
0x18000d7fd  mov     [rsp+268h+var_28], rax
0x18000d805  mov     rax, [rcx]
0x18000d808  mov     rsi, rdx
0x18000d80b  lea     rdx, [rsp+268h+var_240]
0x18000d810  mov     [rsp+268h+var_240], 0
0x18000d819  mov     ebp, r8d
0x18000d81c  mov     rdi, rcx
0x18000d81f  mov     rax, [rax+60h]
0x18000d823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d828  mov     ebx, eax
0x18000d82a  test    eax, eax
0x18000d82c  js      loc_18000D8DF
0x18000d832  mov     rcx, rsi; struct _TASK_TRIGGER *
0x18000d835  call    ?FixupRandomTrigger@@YAXPEAU_TASK_TRIGGER@@@Z; FixupRandomTrigger(_TASK_TRIGGER *)
0x18000d83a  mov     rcx, [rsp+268h+var_240]
0x18000d83f  mov     rdx, rsi
0x18000d842  mov     rax, [rcx]
0x18000d845  mov     rax, [rax+18h]
0x18000d849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d84e  mov     rcx, [rsp+268h+var_240]
0x18000d853  mov     ebx, eax
0x18000d855  mov     rax, [rcx]
0x18000d858  mov     rax, [rax+10h]
0x18000d85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d861  test    ebx, ebx
0x18000d863  js      short loc_18000D8DF
0x18000d865  xor     r9d, r9d; dwReserved
0x18000d868  mov     [rsp+268h+dwFlags], 0
0x18000d870  mov     r8d, 104h; cchNameLen
0x18000d876  lea     rdx, [rsp+268h+szConnectionName]; lpszConnectionName
0x18000d87b  lea     rcx, [rsp+268h+dwFlags]; lpdwFlags
0x18000d880  call    cs:__imp_InternetGetConnectedStateExW
0x18000d886  mov     r8d, [rsp+268h+dwFlags]
0x18000d88b  mov     rcx, rdi
0x18000d88e  mov     r9, [rdi]
0x18000d891  and     r8d, 1
0x18000d895  mov     eax, r8d
0x18000d898  neg     eax
0x18000d89a  lea     rax, [rsp+268h+szConnectionName]
0x18000d89f  sbb     rdx, rdx
0x18000d8a2  and     rdx, rax
0x18000d8a5  mov     rax, [r9+30h]
0x18000d8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8ae  mov     ebx, eax
0x18000d8b0  test    eax, eax
0x18000d8b2  js      short loc_18000D8DF
0x18000d8b4  mov     rax, [rdi]
0x18000d8b7  mov     edx, ebp
0x18000d8b9  mov     rcx, rdi
0x18000d8bc  mov     rax, [rax+20h]
0x18000d8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8c5  mov     ebx, eax
0x18000d8c7  test    eax, eax
0x18000d8c9  js      short loc_18000D8DF
0x18000d8cb  mov     rax, [rdi]
0x18000d8ce  mov     rcx, rdi
0x18000d8d1  mov     rax, [rax+0A0h]
0x18000d8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8dd  mov     ebx, eax
0x18000d8df  mov     eax, ebx
0x18000d8e1  mov     rcx, [rsp+268h+var_28]
0x18000d8e9  xor     rcx, rsp; StackCookie
0x18000d8ec  call    __security_check_cookie
0x18000d8f1  mov     rbx, [rsp+268h+arg_18]
0x18000d8f9  add     rsp, 250h
0x18000d900  pop     rdi
0x18000d901  pop     rsi
0x18000d902  pop     rbp
0x18000d903  retn
```
