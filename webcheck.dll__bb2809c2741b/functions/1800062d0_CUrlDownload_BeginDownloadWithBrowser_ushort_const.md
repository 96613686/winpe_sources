# CUrlDownload::BeginDownloadWithBrowser(ushort const *)

- ea: `0x1800062d0`
- end: `0x1800063cb`
- name: `?BeginDownloadWithBrowser@CUrlDownload@@IEAAJPEBG@Z`
- size: `251`
- prototype: `__int64 __fastcall(CUrlDownload *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005f44`
- `0x1800060f8`

## callees

- `0x1800062d0`
- `0x1800068e8`
- `0x180006c60`
- `0x180007370`
- `0x1800085c0`
- `0x18002a010`

## import_xrefs

- `ole32!CreateBindCtx` at `0x180006323`
- `ole32!CreateBindCtx` at `0x180006323`
- `urlmon!CreateURLMonikerEx` at `0x180006316`
- `urlmon!CreateURLMonikerEx` at `0x180006316`

## pseudocode

```c
__int64 __fastcall CUrlDownload::BeginDownloadWithBrowser(CUrlDownload *this, const unsigned __int16 *a2)
{
  HRESULT Browser; // edi
  LPBC ppbc; // [rsp+50h] [rbp+18h] BYREF
  LPMONIKER ppmk; // [rsp+58h] [rbp+20h] BYREF

  Browser = CUrlDownload::GetBrowser(this);
  if ( Browser >= 0 )
  {
    ppmk = 0;
    ppbc = 0;
    CreateURLMonikerEx(0, a2, &ppmk, 1u);
    Browser = CreateBindCtx(0, &ppbc);
    if ( Browser >= 0 )
    {
      InsertHistoricalCodepageIntoBindCtx(a2, ppbc);
      Browser = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPMONIKER, LPBC, _DWORD))(**((_QWORD **)this + 13) + 40LL))(
                  *((_QWORD *)this + 13),
                  0,
                  ppmk,
                  ppbc,
                  0);
      if ( Browser >= 0 )
        *((_DWORD *)this + 32) = 1;
    }
    if ( ppmk )
      ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
    if ( ppbc )
      ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    if ( Browser < 0 )
    {
      CUrlDownload::CleanUpBrowser(this);
    }
    else
    {
      *((_DWORD *)this + 38) = 1;
      CUrlDownload::StartTimer(this);
    }
  }
  return (unsigned int)Browser;
}

```

## disassembly

```asm
0x1800062d0  mov     [rsp+arg_0], rbx
0x1800062d5  mov     [rsp+arg_8], rsi
0x1800062da  push    rdi
0x1800062db  sub     rsp, 30h
0x1800062df  mov     rsi, rdx
0x1800062e2  mov     rbx, rcx
0x1800062e5  call    ?GetBrowser@CUrlDownload@@IEAAJXZ; CUrlDownload::GetBrowser(void)
0x1800062ea  mov     edi, eax
0x1800062ec  test    eax, eax
0x1800062ee  js      loc_1800063B9
0x1800062f4  mov     r9d, 1; dwFlags
0x1800062fa  mov     [rsp+38h+ppmk], 0
0x180006303  lea     r8, [rsp+38h+ppmk]; ppmk
0x180006308  mov     [rsp+38h+ppbc], 0
0x180006311  mov     rdx, rsi; szURL
0x180006314  xor     ecx, ecx; pMkCtx
0x180006316  call    cs:__imp_CreateURLMonikerEx
0x18000631c  lea     rdx, [rsp+38h+ppbc]; ppbc
0x180006321  xor     ecx, ecx; reserved
0x180006323  call    cs:__imp_CreateBindCtx
0x180006329  mov     edi, eax
0x18000632b  test    eax, eax
0x18000632d  js      short loc_180006370
0x18000632f  mov     rdx, [rsp+38h+ppbc]; struct IBindCtx *
0x180006334  mov     rcx, rsi; unsigned __int16 *
0x180006337  call    ?InsertHistoricalCodepageIntoBindCtx@@YAJPEBGPEAUIBindCtx@@@Z; InsertHistoricalCodepageIntoBindCtx(ushort const *,IBindCtx *)
0x18000633c  mov     rcx, [rbx+68h]
0x180006340  xor     edx, edx
0x180006342  mov     r9, [rsp+38h+ppbc]
0x180006347  mov     r8, [rsp+38h+ppmk]
0x18000634c  mov     [rsp+38h+var_18], 0
0x180006354  mov     rax, [rcx]
0x180006357  mov     rax, [rax+28h]
0x18000635b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006360  mov     edi, eax
0x180006362  test    eax, eax
0x180006364  js      short loc_180006370
0x180006366  mov     dword ptr [rbx+80h], 1
0x180006370  mov     rcx, [rsp+38h+ppmk]
0x180006375  test    rcx, rcx
0x180006378  jz      short loc_180006386
0x18000637a  mov     rax, [rcx]
0x18000637d  mov     rax, [rax+10h]
0x180006381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006386  mov     rcx, [rsp+38h+ppbc]
0x18000638b  test    rcx, rcx
0x18000638e  jz      short loc_18000639C
0x180006390  mov     rax, [rcx]
0x180006393  mov     rax, [rax+10h]
0x180006397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000639c  mov     rcx, rbx; this
0x18000639f  test    edi, edi
0x1800063a1  js      short loc_1800063B4
0x1800063a3  mov     dword ptr [rbx+98h], 1
0x1800063ad  call    ?StartTimer@CUrlDownload@@IEAAXXZ; CUrlDownload::StartTimer(void)
0x1800063b2  jmp     short loc_1800063B9
0x1800063b4  call    ?CleanUpBrowser@CUrlDownload@@IEAAXXZ; CUrlDownload::CleanUpBrowser(void)
0x1800063b9  mov     rbx, [rsp+38h+arg_0]
0x1800063be  mov     eax, edi
0x1800063c0  mov     rsi, [rsp+38h+arg_8]
0x1800063c5  add     rsp, 30h
0x1800063c9  pop     rdi
0x1800063ca  retn
```
