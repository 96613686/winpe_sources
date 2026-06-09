# CDateTimeOm::AddInternetPageAsync(void)

- ea: `0x18001b52c`
- end: `0x18001b5ae`
- name: `?AddInternetPageAsync@CDateTimeOm@@QEAAJXZ`
- size: `130`
- prototype: `__int64 __fastcall(CDateTimeOm *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a670`
- `0x1800103a0`

## callees

- `0x18001b52c`
- `0x18001bb1c`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x18001b58b`
- `SHLWAPI!__imp_SHCreateThread` at `0x18001b58b`
- `SHLWAPI!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x18001b569`
- `SHLWAPI!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x18001b569`

## pseudocode

```c
__int64 __fastcall CDateTimeOm::AddInternetPageAsync(CDateTimeOm *this)
{
  unsigned int v1; // ebx
  volatile signed __int32 *v2; // rdi

  v1 = -2147467259;
  if ( !dword_18003AD28 )
  {
    v2 = (volatile signed __int32 *)g_pom;
    dword_18003AD28 = 1;
    if ( SHRegGetBoolValueFromHKCUHKLM(
           (LPCSTR)L"Software\\Microsoft\\Windows\\CurrentVersion\\DateTime",
           L"Support Internet Time") )
    {
      _InterlockedIncrement(v2 + 120);
      if ( SHCreateThread(CDateTimeOm::s_AsyncCheckDCThreadProc, (void *)v2, 0x11u, 0) )
        return 0;
      else
        CDateTimeOm::Release((CDateTimeOm *)v2);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18001b52c  mov     [rsp+arg_0], rbx
0x18001b531  push    rdi
0x18001b532  sub     rsp, 20h
0x18001b536  cmp     cs:dword_18003AD28, 0
0x18001b53d  mov     ebx, 80004005h
0x18001b542  jnz     short loc_18001B5A1
0x18001b544  mov     rdi, cs:?g_pom@@3PEAVCDateTimeOm@@EA; CDateTimeOm * g_pom
0x18001b54b  lea     rdx, aSupportInterne; "Support Internet Time"
0x18001b552  mov     r8d, 1
0x18001b558  mov     cs:dword_18003AD28, 1
0x18001b562  lea     rcx, pszPrefix; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001b569  call    cs:__imp_SHRegGetBoolValueFromHKCUHKLM
0x18001b56f  test    eax, eax
0x18001b571  jz      short loc_18001B5A1
0x18001b573  lock inc dword ptr [rdi+1E0h]
0x18001b57a  xor     r9d, r9d; pfnCallback
0x18001b57d  lea     rcx, ?s_AsyncCheckDCThreadProc@CDateTimeOm@@CAKPEAX@Z; pfnThreadProc
0x18001b584  mov     rdx, rdi; pData
0x18001b587  lea     r8d, [r9+11h]; flags
0x18001b58b  call    cs:__imp_SHCreateThread
0x18001b591  test    eax, eax
0x18001b593  jz      short loc_18001B599
0x18001b595  xor     ebx, ebx
0x18001b597  jmp     short loc_18001B5A1
0x18001b599  mov     rcx, rdi; this
0x18001b59c  call    ?Release@CDateTimeOm@@QEAAKXZ; CDateTimeOm::Release(void)
0x18001b5a1  mov     eax, ebx
0x18001b5a3  mov     rbx, [rsp+28h+arg_0]
0x18001b5a8  add     rsp, 20h
0x18001b5ac  pop     rdi
0x18001b5ad  retn
```
