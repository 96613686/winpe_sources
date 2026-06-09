# CVssResource::LoadStringW(uint)

- ea: `0x1800356fc`
- end: `0x1800358eb`
- name: `?LoadStringW@CVssResource@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z`
- size: `495`
- prototype: `__int64 __fastcall(__int64, __int64, UINT)`
- caller_count: `6`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180034278`
- `0x180034324`
- `0x180034754`
- `0x1800348b4`
- `0x180034a4c`
- `0x180034f3c`

## callees

- `0x180001580`
- `0x18000212c`
- `0x18002e79c`
- `0x1800334f8`
- `0x1800336cc`
- `0x180035680`
- `0x1800356fc`
- `0x180036218`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003575d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003575d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035821`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180035813`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180035813`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035747`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035747`

## string_xrefs

- `0x1800357bc`: `Error loading VSS.DLL [0x%08lx]`
- `0x180035884`: `Error loading VSS.DLL resource with ID = 0x%08lx [0x%08lx]`
- `0x180035740`: `vsstrace.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssResource::LoadStringW(__int64 a1, __int64 a2, UINT a3)
{
  DWORD LastError; // ebx
  int v6; // ecx
  WCHAR *v7; // r8
  DWORD v8; // ebx
  int v9; // ecx
  const unsigned __int16 *v12; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v13; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v14; // [rsp+50h] [rbp-B0h]
  int v15; // [rsp+58h] [rbp-A8h]
  int v16; // [rsp+5Ch] [rbp-A4h]
  int v17; // [rsp+60h] [rbp-A0h]
  _BYTE v18[120]; // [rsp+68h] [rbp-98h] BYREF
  int v19; // [rsp+E0h] [rbp-20h]
  LPWSTR lpBuffer[2]; // [rsp+E8h] [rbp-18h] BYREF
  int cchBufferMax[4]; // [rsp+F8h] [rbp-8h]

  if ( !`CVssResource::LoadStringW'::`2'::hMod )
  {
    `CVssResource::LoadStringW'::`2'::hMod = LoadLibraryExW(L"vsstrace.dll", 0, 2u);
    if ( !`CVssResource::LoadStringW'::`2'::hMod )
    {
      LastError = GetLastError();
      v12 = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
      v13 = L"CVssResource::LoadStringW";
      v14 = L"TRCTRCC";
      v15 = 76;
      v16 = 11;
      v17 = 255;
      v19 = 0x1000000;
      memset_0(v18, 0, sizeof(v18));
      CVssFunctionTracer::StaticTrace(&v12, 40, L"VssLoadString", L"Error loading VSS.DLL [0x%08lx]", LastError);
      InternalThrow(v6);
    }
  }
  *(_OWORD *)lpBuffer = 0;
  *(_OWORD *)cchBufferMax = 0;
  std::wstring::_Construct<0,unsigned short>(lpBuffer);
  v7 = (WCHAR *)lpBuffer;
  if ( *(_QWORD *)&cchBufferMax[2] > 7u )
    v7 = lpBuffer[0];
  if ( !LoadStringW(`CVssResource::LoadStringW'::`2'::hMod, a3, v7, cchBufferMax[0]) )
  {
    v8 = GetLastError();
    v12 = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
    v13 = L"CVssResource::LoadStringW";
    v14 = L"TRCTRCC";
    v15 = 97;
    v16 = 11;
    v17 = 255;
    v19 = 0x1000000;
    memset_0(v18, 0, sizeof(v18));
    CVssFunctionTracer::StaticTrace(
      &v12,
      40,
      L"VssLoadString",
      L"Error loading VSS.DLL resource with ID = 0x%08lx [0x%08lx]",
      a3,
      v8,
      a2);
    InternalThrow(v9);
  }
  std::wstring::wstring(a2);
  std::wstring::_Tidy_deallocate(lpBuffer);
  return a2;
}

```

## disassembly

```asm
0x1800356fc  mov     [rsp-8+arg_0], rbx
0x180035701  mov     [rsp-8+arg_18], rdi
0x180035706  push    rbp
0x180035707  lea     rbp, [rsp-10h]
0x18003570c  sub     rsp, 110h
0x180035713  mov     rax, cs:__security_cookie
0x18003571a  xor     rax, rsp
0x18003571d  mov     [rbp+10h+var_8], rax
0x180035721  mov     edi, r8d
0x180035724  mov     rbx, rdx
0x180035727  mov     [rsp+110h+var_E0], rdx
0x18003572c  cmp     cs:?hMod@?1??LoadStringW@CVssResource@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z@4PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * `CVssResource::LoadStringW(uint)'::`2'::hMod
0x180035734  jnz     loc_1800357DF
0x18003573a  xor     edx, edx; hFile
0x18003573c  lea     r8d, [rdx+2]; dwFlags
0x180035740  lea     rcx, aVsstraceDll_0; "vsstrace.dll"
0x180035747  call    cs:__imp_LoadLibraryExW
0x18003574d  mov     cs:?hMod@?1??LoadStringW@CVssResource@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `CVssResource::LoadStringW(uint)'::`2'::hMod
0x180035754  test    rax, rax
0x180035757  jnz     loc_1800357DF
0x18003575d  call    cs:__imp_GetLastError
0x180035763  mov     ebx, eax
0x180035765  lea     rax, aBaseStorVssMod_0; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x18003576c  mov     [rsp+110h+var_D0], rax
0x180035771  lea     rax, aCvssresourceLo; "CVssResource::LoadStringW"
0x180035778  mov     [rsp+110h+var_C8], rax
0x18003577d  lea     rax, aTrctrcc; "TRCTRCC"
0x180035784  mov     [rsp+110h+var_C0], rax
0x180035789  mov     [rsp+110h+var_B8], 4Ch ; 'L'
0x180035791  mov     [rsp+110h+var_B4], 0Bh
0x180035799  mov     [rsp+110h+var_B0], 0FFh
0x1800357a1  mov     [rbp+10h+var_30], 1000000h
0x1800357a8  xor     edx, edx; Val
0x1800357aa  lea     r8d, [rdx+78h]; Size
0x1800357ae  lea     rcx, [rsp+110h+var_A8]; void *
0x1800357b3  call    memset_0
0x1800357b8  mov     [rsp+110h+var_F0], ebx
0x1800357bc  lea     r9, aErrorLoadingVs_0; "Error loading VSS.DLL [0x%08lx]"
0x1800357c3  lea     r8, aVssloadstring; "VssLoadString"
0x1800357ca  mov     edx, 28h ; '('
0x1800357cf  lea     rcx, [rsp+110h+var_D0]
0x1800357d4  call    ?StaticTrace@CVssFunctionTracer@@SAXUCVssDebugInfo@@KPEBG1ZZ; CVssFunctionTracer::StaticTrace(CVssDebugInfo,ulong,ushort const *,ushort const *,...)
0x1800357d9  call    ?InternalThrow@@YAXJ@Z; InternalThrow(long)
0x1800357df  xorps   xmm0, xmm0
0x1800357e2  movups  xmmword ptr [rbp+10h+lpBuffer], xmm0
0x1800357e6  xorps   xmm1, xmm1
0x1800357e9  movdqu  xmmword ptr [rbp+10h+cchBufferMax], xmm1
0x1800357ee  lea     rcx, [rbp+10h+lpBuffer]
0x1800357f2  call    ??$_Construct@$0A@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXG_K@Z; std::wstring::_Construct<0,ushort>(ushort,unsigned __int64)
0x1800357f7  nop
0x1800357f8  lea     r8, [rbp+10h+lpBuffer]
0x1800357fc  cmp     qword ptr [rbp+10h+cchBufferMax+8], 7
0x180035801  cmova   r8, [rbp+10h+lpBuffer]; lpBuffer
0x180035806  mov     r9d, [rbp+10h+cchBufferMax]; cchBufferMax
0x18003580a  mov     edx, edi; uID
0x18003580c  mov     rcx, cs:?hMod@?1??LoadStringW@CVssResource@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z@4PEAUHINSTANCE__@@EA; hInstance
0x180035813  call    cs:__imp_LoadStringW
0x180035819  test    eax, eax
0x18003581b  jnz     loc_1800358A7
0x180035821  call    cs:__imp_GetLastError
0x180035827  mov     ebx, eax
0x180035829  lea     rax, aBaseStorVssMod_0; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x180035830  mov     [rsp+110h+var_D0], rax
0x180035835  lea     rax, aCvssresourceLo; "CVssResource::LoadStringW"
0x18003583c  mov     [rsp+110h+var_C8], rax
0x180035841  lea     rax, aTrctrcc; "TRCTRCC"
0x180035848  mov     [rsp+110h+var_C0], rax
0x18003584d  mov     [rsp+110h+var_B8], 61h ; 'a'
0x180035855  mov     [rsp+110h+var_B4], 0Bh
0x18003585d  mov     [rsp+110h+var_B0], 0FFh
0x180035865  mov     [rbp+10h+var_30], 1000000h
0x18003586c  xor     edx, edx; Val
0x18003586e  lea     r8d, [rdx+78h]; Size
0x180035872  lea     rcx, [rsp+110h+var_A8]; void *
0x180035877  call    memset_0
0x18003587c  mov     [rsp+110h+var_E8], ebx
0x180035880  mov     [rsp+110h+var_F0], edi
0x180035884  lea     r9, aErrorLoadingVs; "Error loading VSS.DLL resource with ID "...
0x18003588b  lea     r8, aVssloadstring; "VssLoadString"
0x180035892  mov     edx, 28h ; '('
0x180035897  lea     rcx, [rsp+110h+var_D0]
0x18003589c  call    ?StaticTrace@CVssFunctionTracer@@SAXUCVssDebugInfo@@KPEBG1ZZ; CVssFunctionTracer::StaticTrace(CVssDebugInfo,ulong,ushort const *,ushort const *,...)
0x1800358a1  call    ?InternalThrow@@YAXJ@Z; InternalThrow(long)
0x1800358a7  lea     rdx, [rbp+10h+lpBuffer]
0x1800358ab  cmp     qword ptr [rbp+10h+cchBufferMax+8], 7
0x1800358b0  cmova   rdx, [rbp+10h+lpBuffer]
0x1800358b5  mov     rcx, rbx
0x1800358b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800358bd  nop
0x1800358be  lea     rcx, [rbp+10h+lpBuffer]
0x1800358c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800358c7  mov     rax, rbx
0x1800358ca  mov     rcx, [rbp+10h+var_8]
0x1800358ce  xor     rcx, rsp; StackCookie
0x1800358d1  call    __security_check_cookie
0x1800358d6  lea     r11, [rsp+110h+var_s0]
0x1800358de  mov     rbx, [r11+10h]
0x1800358e2  mov     rdi, [r11+28h]
0x1800358e6  mov     rsp, r11
0x1800358e9  pop     rbp
0x1800358ea  retn
```
