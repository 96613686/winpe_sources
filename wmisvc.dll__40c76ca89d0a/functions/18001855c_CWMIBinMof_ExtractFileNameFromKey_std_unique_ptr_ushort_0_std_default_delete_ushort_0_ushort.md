# CWMIBinMof::ExtractFileNameFromKey(std::unique_ptr<ushort [0],std::default_delete<ushort [0]>> &,ushort *)

- ea: `0x18001855c`
- end: `0x18001864c`
- name: `?ExtractFileNameFromKey@CWMIBinMof@@AEAAHAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@PEAG@Z`
- size: `240`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003b94`
- `0x1800186bc`

## callees

- `0x1800021f0`
- `0x180004120`
- `0x1800079f0`
- `0x180010100`
- `0x18001855c`
- `0x180019948`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800185ff`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800185ff`

## pseudocode

```c
__int64 __fastcall CWMIBinMof::ExtractFileNameFromKey(wchar_t *a1, unsigned __int16 **a2, const unsigned __int16 *a3)
{
  unsigned int v5; // edi
  wchar_t *v6; // rbx
  wchar_t **v7; // r8
  wchar_t *v8; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // rsi
  void *v11; // rax
  wchar_t *String; // [rsp+40h] [rbp+8h] BYREF

  String = a1;
  CAutoWChar::CAutoWChar((CAutoWChar *)&String, 1040);
  v5 = 0;
  v6 = String;
  if ( String && a3 && (int)StringCchCopyW(String, 0x410u, a3) >= 0 )
  {
    v8 = wcstok_mvcrt_legacy_two_parameter_form(v6, L"[", v7);
    if ( v8 )
      StringCchCopyW(v6, 0x410u, v8);
    v9 = -1;
    do
      ++v9;
    while ( v6[v9] );
    v10 = (int)v9 + 1;
    v11 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v10, 2u));
    std::unique_ptr<unsigned short [0]>::reset(a2, v11);
    if ( *a2 && (int)StringCchCopyW(*a2, v10, v6) >= 0 )
      v5 = 1;
  }
  CAutoWChar::~CAutoWChar((void **)&String);
  return v5;
}

```

## disassembly

```asm
0x18001855c  mov     rax, rsp
0x18001855f  mov     [rax+10h], rbx
0x180018563  mov     [rax+18h], rbp
0x180018567  mov     [rax+8], rcx
0x18001856b  push    rsi
0x18001856c  push    rdi
0x18001856d  push    r14
0x18001856f  sub     rsp, 20h
0x180018573  mov     rsi, r8
0x180018576  mov     r14, rdx
0x180018579  mov     edx, 410h; int
0x18001857e  lea     rcx, [rax+8]; this
0x180018582  call    ??0CAutoWChar@@QEAA@H@Z; CAutoWChar::CAutoWChar(int)
0x180018587  nop
0x180018588  xor     ebp, ebp
0x18001858a  mov     edi, ebp
0x18001858c  mov     rbx, [rsp+38h+String]
0x180018591  test    rbx, rbx
0x180018594  jz      loc_18001862D
0x18001859a  test    rsi, rsi
0x18001859d  jz      loc_18001862D
0x1800185a3  mov     r8, rsi; unsigned __int16 *
0x1800185a6  mov     edx, 410h; unsigned __int64
0x1800185ab  mov     rcx, rbx; unsigned __int16 *
0x1800185ae  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800185b3  test    eax, eax
0x1800185b5  js      short loc_18001862D
0x1800185b7  lea     rdx, asc_180025CF0; "["
0x1800185be  mov     rcx, rbx; String
0x1800185c1  call    wcstok_mvcrt_legacy_two_parameter_form
0x1800185c6  test    rax, rax
0x1800185c9  jz      short loc_1800185DB
0x1800185cb  mov     r8, rax; unsigned __int16 *
0x1800185ce  mov     edx, 410h; unsigned __int64
0x1800185d3  mov     rcx, rbx; unsigned __int16 *
0x1800185d6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800185db  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800185df  mov     rax, rcx
0x1800185e2  inc     rax
0x1800185e5  cmp     [rbx+rax*2], bp
0x1800185e9  jnz     short loc_1800185E2
0x1800185eb  inc     eax
0x1800185ed  movsxd  rsi, eax
0x1800185f0  mov     eax, 2
0x1800185f5  mul     rsi
0x1800185f8  cmovb   rax, rcx
0x1800185fc  mov     rcx, rax
0x1800185ff  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180018605  mov     rdx, rax
0x180018608  mov     rcx, r14
0x18001860b  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort [0]>::reset(ushort *)
0x180018610  mov     rcx, [r14]; unsigned __int16 *
0x180018613  test    rcx, rcx
0x180018616  jz      short loc_18001862D
0x180018618  mov     r8, rbx; unsigned __int16 *
0x18001861b  mov     rdx, rsi; unsigned __int64
0x18001861e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018623  mov     ecx, 1
0x180018628  test    eax, eax
0x18001862a  cmovns  edi, ecx
0x18001862d  lea     rcx, [rsp+38h+String]; this
0x180018632  call    ??1CAutoWChar@@QEAA@XZ; CAutoWChar::~CAutoWChar(void)
0x180018637  mov     eax, edi
0x180018639  mov     rbx, [rsp+38h+arg_8]
0x18001863e  mov     rbp, [rsp+38h+arg_10]
0x180018643  add     rsp, 20h
0x180018647  pop     r14
0x180018649  pop     rdi
0x18001864a  pop     rsi
0x18001864b  retn
```
