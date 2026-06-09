# wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(void)

- ea: `0x180015a08`
- end: `0x180015a34`
- name: `?reset@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180014df8`
- `0x180014ec0`

## callees

- `0x180015a08`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180015a19`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180015a19`

## pseudocode

```c
__int64 __fastcall wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
  {
    result = UMgrFreeSessionUsers();
    *a1 = 0;
    a1[1] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180015a08  push    rbx
0x180015a0a  sub     rsp, 20h
0x180015a0e  mov     rbx, rcx
0x180015a11  mov     rcx, [rcx]
0x180015a14  test    rcx, rcx
0x180015a17  jz      short loc_180015A2E
0x180015a19  call    cs:__imp_UMgrFreeSessionUsers
0x180015a1f  mov     qword ptr [rbx], 0
0x180015a26  mov     qword ptr [rbx+8], 0
0x180015a2e  add     rsp, 20h
0x180015a32  pop     rbx
0x180015a33  retn
```
