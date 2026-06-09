# CNavigateButton::NavigateBack(IUnknown *)

- ea: `0x180051c2c`
- end: `0x180051ce3`
- name: `?NavigateBack@CNavigateButton@@SAXPEAUIUnknown@@@Z`
- size: `183`
- prototype: `void __fastcall(struct IUnknown *)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x180009130`
- `0x1800093a0`
- `0x1800226d0`
- `0x180022ba0`
- `0x1800241a0`
- `0x18003c7dc`

## callees

- `0x180051c2c`
- `0x180057010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180051c51`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180051c51`
- `SHLWAPI!__imp_IUnknown_QueryServiceForWebBrowserApp` at `0x180051c96`
- `SHLWAPI!__imp_IUnknown_QueryServiceForWebBrowserApp` at `0x180051c96`

## pseudocode

```c
void __fastcall CNavigateButton::NavigateBack(struct IUnknown *a1)
{
  __int64 v2; // [rsp+38h] [rbp+10h] BYREF
  void *ppvOut; // [rsp+40h] [rbp+18h] BYREF

  ppvOut = 0;
  if ( IUnknown_QueryService(
         a1,
         (const GUID *const)&SID_STopLevelBrowser,
         &GUID_000214e2_0000_0000_c000_000000000046,
         &ppvOut) >= 0 )
  {
    if ( (*(int (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)ppvOut + 88LL))(ppvOut, 0, 0x4000) < 0 )
    {
      v2 = 0;
      if ( (int)IUnknown_QueryServiceForWebBrowserApp(a1, &GUID_0002df05_0000_0000_c000_000000000046, &v2) >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 256LL))(v2);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
}

```

## disassembly

```asm
0x180051c2c  push    rbx
0x180051c2e  sub     rsp, 20h
0x180051c32  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x180051c37  mov     [rsp+28h+ppvOut], 0
0x180051c40  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x180051c47  mov     rbx, rcx
0x180051c4a  lea     rdx, SID_STopLevelBrowser; guidService
0x180051c51  call    cs:__imp_IUnknown_QueryService
0x180051c58  nop     dword ptr [rax+rax+00h]
0x180051c5d  test    eax, eax
0x180051c5f  js      short loc_180051CDC
0x180051c61  mov     rcx, [rsp+28h+ppvOut]
0x180051c66  xor     edx, edx
0x180051c68  mov     r8d, 4000h
0x180051c6e  mov     rax, [rcx]
0x180051c71  mov     rax, [rax+58h]
0x180051c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c7a  test    eax, eax
0x180051c7c  jns     short loc_180051CCB
0x180051c7e  lea     r8, [rsp+28h+arg_8]
0x180051c83  mov     [rsp+28h+arg_8], 0
0x180051c8c  lea     rdx, _GUID_0002df05_0000_0000_c000_000000000046
0x180051c93  mov     rcx, rbx
0x180051c96  call    cs:__imp_IUnknown_QueryServiceForWebBrowserApp
0x180051c9d  nop     dword ptr [rax+rax+00h]
0x180051ca2  test    eax, eax
0x180051ca4  js      short loc_180051CCB
0x180051ca6  mov     rcx, [rsp+28h+arg_8]
0x180051cab  mov     rax, [rcx]
0x180051cae  mov     rax, [rax+100h]
0x180051cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051cba  mov     rcx, [rsp+28h+arg_8]
0x180051cbf  mov     rax, [rcx]
0x180051cc2  mov     rax, [rax+10h]
0x180051cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051ccb  mov     rcx, [rsp+28h+ppvOut]
0x180051cd0  mov     rax, [rcx]
0x180051cd3  mov     rax, [rax+10h]
0x180051cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051cdc  add     rsp, 20h
0x180051ce0  pop     rbx
0x180051ce1  retn
```
