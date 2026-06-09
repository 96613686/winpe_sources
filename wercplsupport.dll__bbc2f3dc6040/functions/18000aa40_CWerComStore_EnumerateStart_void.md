# CWerComStore::EnumerateStart(void)

- ea: `0x18000aa40`
- end: `0x18000aae7`
- name: `?EnumerateStart@CWerComStore@@UEAAJXZ`
- size: `167`
- prototype: `__int64 __fastcall(CWerComStore *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006c9c`
- `0x180007d20`
- `0x180007fe0`
- `0x18000aa40`
- `0x18000e3fc`

## import_xrefs

- `wer!WerpEnumerateStoreStart` at `0x18000aab9`
- `wer!WerpEnumerateStoreStart` at `0x18000aab9`

## pseudocode

```c
__int64 __fastcall CWerComStore::EnumerateStart(CWerComStore *this)
{
  int WerStoreApiLock; // ebx
  int v4; // [rsp+38h] [rbp+10h] BYREF
  __int64 v5; // [rsp+40h] [rbp+18h] BYREF

  v4 = 2;
  WerStoreApiLock = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v4);
  if ( WerStoreApiLock >= 0 )
  {
    v5 = 0;
    WerStoreApiLock = CWerStoreApiAutoLock::TryGetWerStoreApiLock(
                        (CWerStoreApiAutoLock *)&v5,
                        (CWerComStore *)((char *)this - 24));
    if ( WerStoreApiLock >= 0 )
    {
      WerStoreApiLock = WerpEnumerateStoreStart(*((_QWORD *)this + 1));
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        85,
        WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
        (unsigned int)WerStoreApiLock);
    }
    if ( v5 )
      _InterlockedExchange((volatile __int32 *)(v5 + 40), 0);
  }
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v4);
  return (unsigned int)WerStoreApiLock;
}

```

## disassembly

```asm
0x18000aa40  mov     [rsp+arg_0], rbx
0x18000aa45  push    rdi
0x18000aa46  sub     rsp, 20h
0x18000aa4a  mov     rdi, rcx
0x18000aa4d  mov     [rsp+28h+arg_8], 2
0x18000aa55  lea     rcx, [rsp+28h+arg_8]; this
0x18000aa5a  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18000aa5f  mov     ebx, eax
0x18000aa61  test    eax, eax
0x18000aa63  js      short loc_18000AAD0
0x18000aa65  lea     rdx, [rdi-18h]; struct CWerComStore *
0x18000aa69  mov     [rsp+28h+arg_10], 0
0x18000aa72  lea     rcx, [rsp+28h+arg_10]; this
0x18000aa77  call    ?TryGetWerStoreApiLock@CWerStoreApiAutoLock@@QEAAJPEAVCWerComStore@@@Z; CWerStoreApiAutoLock::TryGetWerStoreApiLock(CWerComStore *)
0x18000aa7c  mov     ebx, eax
0x18000aa7e  test    eax, eax
0x18000aa80  jns     short loc_18000AAB5
0x18000aa82  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa89  lea     rax, WPP_GLOBAL_Control
0x18000aa90  cmp     rcx, rax
0x18000aa93  jz      short loc_18000AAC1
0x18000aa95  test    byte ptr [rcx+1Ch], 1
0x18000aa99  jz      short loc_18000AAC1
0x18000aa9b  mov     rcx, [rcx+10h]
0x18000aa9f  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000aaa6  mov     edx, 55h ; 'U'
0x18000aaab  mov     r9d, ebx
0x18000aaae  call    WPP_SF_d
0x18000aab3  jmp     short loc_18000AAC1
0x18000aab5  mov     rcx, [rdi+8]
0x18000aab9  call    cs:__imp_WerpEnumerateStoreStart
0x18000aabf  mov     ebx, eax
0x18000aac1  mov     rax, [rsp+28h+arg_10]
0x18000aac6  test    rax, rax
0x18000aac9  jz      short loc_18000AAD0
0x18000aacb  xor     ecx, ecx
0x18000aacd  xchg    ecx, [rax+28h]
0x18000aad0  lea     rcx, [rsp+28h+arg_8]; this
0x18000aad5  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18000aada  mov     eax, ebx
0x18000aadc  mov     rbx, [rsp+28h+arg_0]
0x18000aae1  add     rsp, 20h
0x18000aae5  pop     rdi
0x18000aae6  retn
```
