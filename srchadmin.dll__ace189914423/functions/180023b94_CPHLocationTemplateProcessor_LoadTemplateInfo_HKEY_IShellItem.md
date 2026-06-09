# CPHLocationTemplateProcessor::_LoadTemplateInfo(HKEY__ *,IShellItem *)

- ea: `0x180023b94`
- end: `0x180023cc3`
- name: `?_LoadTemplateInfo@CPHLocationTemplateProcessor@@AEAAJPEAUHKEY__@@PEAUIShellItem@@@Z`
- size: `303`
- prototype: `int(CPHLocationTemplateProcessor *__hidden this, HKEY, struct IShellItem *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180023f48`

## callees

- `0x18001a220`
- `0x180023b94`
- `0x180023d8c`
- `0x180032010`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x180023c18`
- `SHELL32!SHGetKnownFolderPath` at `0x180023c18`
- `SHLWAPI!__imp_IUnknown_Set` at `0x180023bf9`
- `SHLWAPI!__imp_IUnknown_Set` at `0x180023bf9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023ca8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023ca8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023c73`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023c73`

## pseudocode

```c
__int64 __fastcall CPHLocationTemplateProcessor::_LoadTemplateInfo(
        CPHLocationTemplateProcessor *this,
        HKEY a2,
        IUnknown *a3)
{
  const unsigned __int16 **v3; // r14
  int v7; // eax
  HRESULT v8; // ebx
  int v9; // r9d
  DWORD dwOptions; // [rsp+20h] [rbp-48h]
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  v3 = (const unsigned __int16 **)((char *)this + 520);
  if ( a3 )
    v7 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, char *))a3->lpVtbl[1].Release)(a3, 0, (char *)this + 520);
  else
    v7 = _AllocStringWorker<CTCoAllocPolicy>(this, a2, &strIn, 0);
  v8 = v7;
  if ( v7 >= 0 )
  {
    IUnknown_Set((IUnknown **)this + 67, a3);
    v8 = SHGetKnownFolderPath(&FOLDERID_SavedSearches, 0x8000u, 0, (PWSTR *)this + 66);
    if ( v8 >= 0 )
    {
      hKey = 0;
      v8 = RegCreateKeyExW(a2, L"Default", 0, 0, 0, 0x2001Bu, 0, &hKey, 0);
      if ( v8 >= 0 )
      {
        v8 = CLocationTemplate::s_LoadFromRegKey(
               hKey,
               *v3,
               *((const unsigned __int16 **)this + 66),
               v9,
               dwOptions,
               (struct CLocationTemplate **)this + 68);
        RegCloseKey(hKey);
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180023b94  mov     [rsp+arg_0], rbx
0x180023b99  mov     [rsp+arg_8], rbp
0x180023b9e  push    rsi
0x180023b9f  push    rdi
0x180023ba0  push    r14
0x180023ba2  sub     rsp, 50h
0x180023ba6  lea     r14, [rcx+208h]
0x180023bad  mov     rsi, r8
0x180023bb0  mov     rbp, rdx
0x180023bb3  mov     rdi, rcx
0x180023bb6  test    r8, r8
0x180023bb9  jz      short loc_180023BD1
0x180023bbb  mov     rax, [r8]
0x180023bbe  xor     edx, edx
0x180023bc0  mov     r8, r14
0x180023bc3  mov     rcx, rsi
0x180023bc6  mov     rax, [rax+28h]
0x180023bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bcf  jmp     short loc_180023BE5
0x180023bd1  xor     r9d, r9d
0x180023bd4  mov     qword ptr [rsp+68h+samDesired], r14
0x180023bd9  lea     r8, strIn
0x180023be0  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180023be5  mov     ebx, eax
0x180023be7  test    eax, eax
0x180023be9  js      loc_180023CAE
0x180023bef  lea     rcx, [rdi+218h]; ppunk
0x180023bf6  mov     rdx, rsi; punk
0x180023bf9  call    cs:__imp_IUnknown_Set
0x180023bff  lea     rsi, [rdi+210h]
0x180023c06  xor     r8d, r8d; hToken
0x180023c09  mov     r9, rsi; ppszPath
0x180023c0c  lea     rcx, FOLDERID_SavedSearches; rfid
0x180023c13  mov     edx, 8000h; dwFlags
0x180023c18  call    cs:__imp_SHGetKnownFolderPath
0x180023c1e  mov     ebx, eax
0x180023c20  test    eax, eax
0x180023c22  js      loc_180023CAE
0x180023c28  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x180023c31  lea     rax, [rsp+68h+hKey]
0x180023c39  mov     [rsp+68h+phkResult], rax; phkResult
0x180023c3e  lea     rdx, aDefault; "Default"
0x180023c45  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180023c4e  xor     r9d, r9d; lpClass
0x180023c51  mov     [rsp+68h+samDesired], 2001Bh; samDesired
0x180023c59  xor     r8d, r8d; Reserved
0x180023c5c  mov     rcx, rbp; hKey
0x180023c5f  mov     [rsp+68h+dwOptions], 0; int
0x180023c67  mov     [rsp+68h+hKey], 0
0x180023c73  call    cs:__imp_RegCreateKeyExW
0x180023c79  mov     ebx, eax
0x180023c7b  test    eax, eax
0x180023c7d  js      short loc_180023CAE
0x180023c7f  mov     r8, [rsi]; unsigned __int16 *
0x180023c82  lea     rax, [rdi+220h]
0x180023c89  mov     rdx, [r14]; unsigned __int16 *
0x180023c8c  mov     rcx, [rsp+68h+hKey]; HKEY
0x180023c94  mov     qword ptr [rsp+68h+samDesired], rax; struct CLocationTemplate **
0x180023c99  call    ?s_LoadFromRegKey@CLocationTemplate@@SAJPEAUHKEY__@@PEBG1HHPEAPEAV1@@Z; CLocationTemplate::s_LoadFromRegKey(HKEY__ *,ushort const *,ushort const *,int,int,CLocationTemplate * *)
0x180023c9e  mov     rcx, [rsp+68h+hKey]; hKey
0x180023ca6  mov     ebx, eax
0x180023ca8  call    cs:__imp_RegCloseKey
0x180023cae  mov     rbp, [rsp+68h+arg_8]
0x180023cb3  mov     eax, ebx
0x180023cb5  mov     rbx, [rsp+68h+arg_0]
0x180023cba  add     rsp, 50h
0x180023cbe  pop     r14
0x180023cc0  pop     rdi
0x180023cc1  pop     rsi
0x180023cc2  retn
```
