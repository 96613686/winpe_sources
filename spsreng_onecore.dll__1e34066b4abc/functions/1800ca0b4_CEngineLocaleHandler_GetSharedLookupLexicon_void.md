# CEngineLocaleHandler::GetSharedLookupLexicon(void)

- ea: `0x1800ca0b4`
- end: `0x1800ca113`
- name: `?GetSharedLookupLexicon@CEngineLocaleHandler@@IEAAJXZ`
- size: `95`
- prototype: `__int64 __fastcall(CEngineLocaleHandler *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c916c`
- `0x1800c91c4`

## callees

- `0x1800c8688`
- `0x1800ca0b4`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca100`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca100`

## pseudocode

```c
__int64 __fastcall CEngineLocaleHandler::GetSharedLookupLexicon(CEngineLocaleHandler *this)
{
  int Shared; // ebx
  __int64 v2; // rcx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  Shared = 0;
  if ( !*((_QWORD *)this + 8) )
  {
    v2 = *((_QWORD *)this + 4);
    pv = 0;
    Shared = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v2 + 128LL))(v2, &pv);
    if ( Shared >= 0 )
    {
      Shared = GetSharedObject<CSharedVendorLex>((unsigned __int16 *)pv);
      CoTaskMemFree(pv);
    }
  }
  return (unsigned int)Shared;
}

```

## disassembly

```asm
0x1800ca0b4  mov     [rsp+arg_8], rbx
0x1800ca0b9  push    rdi
0x1800ca0ba  sub     rsp, 20h
0x1800ca0be  xor     ebx, ebx
0x1800ca0c0  lea     rdi, [rcx+40h]
0x1800ca0c4  cmp     [rdi], rbx
0x1800ca0c7  jnz     short loc_1800CA106
0x1800ca0c9  mov     rcx, [rcx+20h]
0x1800ca0cd  lea     rdx, [rsp+28h+pv]
0x1800ca0d2  mov     [rsp+28h+pv], rbx
0x1800ca0d7  mov     rax, [rcx]
0x1800ca0da  mov     rax, [rax+80h]
0x1800ca0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca0e6  mov     ebx, eax
0x1800ca0e8  test    eax, eax
0x1800ca0ea  js      short loc_1800CA106
0x1800ca0ec  mov     rcx, [rsp+28h+pv]; unsigned __int16 *
0x1800ca0f1  mov     rdx, rdi
0x1800ca0f4  call    ??$GetSharedObject@VCSharedVendorLex@@@@YAJPEBGPEAPEBVCSharedVendorLex@@@Z; GetSharedObject<CSharedVendorLex>(ushort const *,CSharedVendorLex const * *)
0x1800ca0f9  mov     rcx, [rsp+28h+pv]; pv
0x1800ca0fe  mov     ebx, eax
0x1800ca100  call    cs:__imp_CoTaskMemFree
0x1800ca106  mov     eax, ebx
0x1800ca108  mov     rbx, [rsp+28h+arg_8]
0x1800ca10d  add     rsp, 20h
0x1800ca111  pop     rdi
0x1800ca112  retn
```
