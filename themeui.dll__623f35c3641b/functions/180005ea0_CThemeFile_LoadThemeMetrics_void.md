# CThemeFile::_LoadThemeMetrics(void)

- ea: `0x180005ea0`
- end: `0x180006200`
- name: `?_LoadThemeMetrics@CThemeFile@@AEAAJXZ`
- size: `864`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005d10`
- `0x1800519e0`
- `0x180051cf0`
- `0x180052db4`

## callees

- `0x180005ea0`
- `0x180006210`
- `0x180007d20`
- `0x18000b78c`
- `0x18000dc20`
- `0x1800104c0`
- `0x180015160`
- `0x180016c40`
- `0x1800358c0`
- `0x1800363a8`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x1800061c2`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x1800061c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800060a4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800060a4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800060c2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006168`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800060c2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000603d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000603d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060d6`
- `OLEAUT32!__imp_SysFreeString` at `0x180005fa2`
- `OLEAUT32!__imp_SysFreeString` at `0x180005fa2`

## string_xrefs

- `0x180006064`: `%SystemRoot%\Resources\Ease of Access Themes\hc2.theme`
- `0x180006070`: `%SystemRoot%\Resources\Ease of Access Themes\hcblack.theme`
- `0x180006058`: `%SystemRoot%\Resources\Ease of Access Themes\hc1.theme`
- `0x18000607b`: `%SystemRoot%\Resources\Ease of Access Themes\hcwhite.theme`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall CThemeFile::_LoadThemeMetrics(CThemeFile *this)
{
  int result; // eax
  bool v3; // r12
  int v4; // ebx
  int v5; // r14d
  unsigned __int8 v6; // al
  unsigned __int8 v7; // cl
  unsigned __int8 v8; // dl
  wchar_t *v9; // rbx
  int v10; // eax
  unsigned int v11; // edx
  void *v12; // rcx
  unsigned __int16 **bIgnoreCase; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v14; // [rsp+28h] [rbp-D8h]
  unsigned int v15; // [rsp+30h] [rbp-D0h]
  wchar_t *Buffer; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+58h] [rbp-A8h]
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  struct ITheme *v22[5]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR String2[264]; // [rsp+90h] [rbp-70h] BYREF

  if ( !*((_QWORD *)this + 6) )
    return -2147467259;
  result = CThemeFile::_LoadDefaultThemeMetrics(this, (CThemeFile *)((char *)this + 68));
  v20 = result;
  if ( result >= 0 )
  {
    v22[0] = 0;
    v3 = 0;
    bstrString = 0;
    Buffer = 0;
    if ( (*(int (__fastcall **)(char *, BSTR *))(*((_QWORD *)this + 2) + 480LL))((char *)this + 16, &bstrString) >= 0
      && CompareStringOrdinal(bstrString, -1, L"DABJDKT", -1, 1) == 2
      && (int)CThemeFile::_getThemeSetting(this, L"VisualStyles", L"ColorStyle", 0, &Buffer) >= 0 )
    {
      v9 = Buffer;
      v10 = HighContrastNumberFromSchemeName(Buffer);
      v22[1] = (struct ITheme *)L"%SystemRoot%\\Resources\\Ease of Access Themes\\hc1.theme";
      v22[2] = (struct ITheme *)L"%SystemRoot%\\Resources\\Ease of Access Themes\\hc2.theme";
      v22[3] = (struct ITheme *)L"%SystemRoot%\\Resources\\Ease of Access Themes\\hcblack.theme";
      v22[4] = (struct ITheme *)L"%SystemRoot%\\Resources\\Ease of Access Themes\\hcwhite.theme";
      if ( v10 <= 0 || (unsigned int)(v10 - 1) >= 4 )
      {
        if ( LoadStringW(g_hinst, 0x7EBu, String2, 260) > 0 )
          v3 = CompareStringOrdinal(v9, -1, String2, -1, 1) != 2;
      }
      else if ( (unsigned int)SHExpandEnvironmentStringsW(v22[v10], String2, 260) )
      {
        CThemeFile_CreateInstance(String2, v22);
      }
      CoTaskMemFree(v9);
    }
    v4 = 0;
    while ( 1 )
    {
      Buffer = 0;
      if ( (*(int (__fastcall **)(char *, _QWORD, wchar_t **))(*((_QWORD *)this + 2) + 496LL))(
             (char *)this + 16,
             *((_QWORD *)&gc_rgSystemColorNames + 2 * v4),
             &Buffer) >= 0 )
        goto LABEL_14;
      if ( v22[0] )
      {
        v5 = (*(__int64 (__fastcall **)(struct ITheme *, _QWORD, wchar_t **))(*(_QWORD *)v22[0] + 496LL))(
               v22[0],
               *((_QWORD *)&gc_rgSystemColorNames + 2 * v4),
               &Buffer);
      }
      else
      {
        if ( !v3 || v4 != 1 )
          goto LABEL_10;
        Buffer = 0;
        v19 = 0;
        v5 = ULongLongMult(0xBu, 2u, &v19);
        if ( v5 >= 0 )
          v5 = CTCoAllocPolicy::Alloc(v12, v11, v19, (void **)&Buffer);
        if ( v5 < 0 )
          goto LABEL_10;
        StringCchCopyNExW(Buffer, 0xBu, L"58 110 165", 0xAu, bIgnoreCase, v14, v15);
      }
      if ( v5 >= 0 )
      {
LABEL_14:
        LODWORD(v19) = 0;
        v18 = 0;
        v17 = 0;
        if ( swscanf_s(Buffer, L"%d %d %d", &v19, &v18, &v17) == 3 )
        {
          v6 = v17;
          v7 = v18;
          v8 = v19;
        }
        else
        {
          v6 = 0;
          v7 = 0;
          v8 = 0;
        }
        *((_DWORD *)this + v4 + 168) = v8 | (v6 << 16) | (v7 << 8);
        CoTaskMemFree(Buffer);
      }
LABEL_10:
      if ( (unsigned int)++v4 >= 0x1F )
      {
        SysFreeString(bstrString);
        return v20;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005ea0  push    rbp
0x180005ea2  push    rbx
0x180005ea3  push    rsi
0x180005ea4  push    rdi
0x180005ea5  push    r12
0x180005ea7  push    r13
0x180005ea9  push    r14
0x180005eab  push    r15
0x180005ead  lea     rbp, [rsp-1B8h]
0x180005eb5  sub     rsp, 2B8h
0x180005ebc  mov     rax, cs:__security_cookie
0x180005ec3  xor     rax, rsp
0x180005ec6  mov     [rbp+1F0h+var_50], rax
0x180005ecd  mov     rdi, rcx
0x180005ed0  cmp     qword ptr [rcx+30h], 0
0x180005ed5  jnz     short loc_180005EFF
0x180005ed7  mov     eax, 80004005h
0x180005edc  mov     rcx, [rbp+1F0h+var_50]
0x180005ee3  xor     rcx, rsp; StackCookie
0x180005ee6  call    __security_check_cookie
0x180005eeb  add     rsp, 2B8h
0x180005ef2  pop     r15
0x180005ef4  pop     r14
0x180005ef6  pop     r13
0x180005ef8  pop     r12
0x180005efa  pop     rdi
0x180005efb  pop     rsi
0x180005efc  pop     rbx
0x180005efd  pop     rbp
0x180005efe  retn
0x180005eff  lea     rdx, [rcx+44h]; struct SYSTEMMETRICSALL *
0x180005f03  call    ?_LoadDefaultThemeMetrics@CThemeFile@@AEAAJPEAUSYSTEMMETRICSALL@@@Z; CThemeFile::_LoadDefaultThemeMetrics(SYSTEMMETRICSALL *)
0x180005f08  mov     [rsp+2F0h+var_298], eax
0x180005f0c  test    eax, eax
0x180005f0e  js      short loc_180005EDC
0x180005f10  xor     r14d, r14d
0x180005f13  mov     [rsp+2F0h+var_288], r14
0x180005f18  xor     r12b, r12b
0x180005f1b  mov     [rsp+2F0h+bstrString], r14
0x180005f20  mov     [rsp+2F0h+Buffer], r14
0x180005f25  mov     rax, [rdi+10h]
0x180005f29  lea     rdx, [rsp+2F0h+bstrString]
0x180005f2e  lea     rcx, [rdi+10h]
0x180005f32  mov     rax, [rax+1E0h]
0x180005f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f3e  test    eax, eax
0x180005f40  jns     loc_18000614A
0x180005f46  mov     ebx, r14d
0x180005f49  lea     r13, ?gc_rgSystemColorNames@@3QBUSYSTEM_COLOR_NAMES@@B; SYSTEM_COLOR_NAMES const near * const gc_rgSystemColorNames
0x180005f50  mov     [rsp+2F0h+Buffer], r14
0x180005f55  movsxd  rsi, ebx
0x180005f58  mov     r14, rsi
0x180005f5b  add     r14, r14
0x180005f5e  mov     rax, [rdi+10h]
0x180005f62  lea     r8, [rsp+2F0h+Buffer]
0x180005f67  mov     rdx, [r13+r14*8+0]
0x180005f6c  lea     rcx, [rdi+10h]
0x180005f70  mov     rax, [rax+1F0h]
0x180005f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f7c  test    eax, eax
0x180005f7e  jns     short loc_180005FD2
0x180005f80  mov     rcx, [rsp+2F0h+var_288]
0x180005f85  test    rcx, rcx
0x180005f88  jnz     short loc_180005FB1
0x180005f8a  test    r12b, r12b
0x180005f8d  jnz     loc_1800061E3
0x180005f93  xor     r14d, r14d
0x180005f96  inc     ebx
0x180005f98  cmp     ebx, 1Fh
0x180005f9b  jb      short loc_180005F50
0x180005f9d  mov     rcx, [rsp+2F0h+bstrString]; bstrString
0x180005fa2  call    cs:__imp_SysFreeString
0x180005fa8  mov     eax, [rsp+2F0h+var_298]
0x180005fac  jmp     loc_180005EDC
0x180005fb1  mov     rax, [rcx]
0x180005fb4  lea     r8, [rsp+2F0h+Buffer]
0x180005fb9  mov     rdx, [r13+r14*8+0]
0x180005fbe  mov     rax, [rax+1F0h]
0x180005fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fca  mov     r14d, eax
0x180005fcd  test    r14d, r14d
0x180005fd0  js      short loc_180005F93
0x180005fd2  xor     r14d, r14d
0x180005fd5  mov     dword ptr [rsp+2F0h+var_2A0], r14d
0x180005fda  mov     [rsp+2F0h+var_2A4], r14d
0x180005fdf  mov     [rsp+2F0h+var_2A8], r14d
0x180005fe4  lea     rax, [rsp+2F0h+var_2A8]
0x180005fe9  mov     qword ptr [rsp+2F0h+bIgnoreCase], rax
0x180005fee  lea     r9, [rsp+2F0h+var_2A4]
0x180005ff3  lea     r8, [rsp+2F0h+var_2A0]
0x180005ff8  lea     rdx, aDDD; "%d %d %d"
0x180005fff  mov     rcx, [rsp+2F0h+Buffer]; Buffer
0x180006004  call    swscanf_s
0x180006009  cmp     eax, 3
0x18000600c  jnz     loc_1800061F1
0x180006012  mov     eax, [rsp+2F0h+var_2A8]
0x180006016  mov     ecx, [rsp+2F0h+var_2A4]
0x18000601a  mov     edx, dword ptr [rsp+2F0h+var_2A0]
0x18000601e  movzx   ecx, cl
0x180006021  shl     ecx, 8
0x180006024  movzx   eax, al
0x180006027  shl     eax, 10h
0x18000602a  or      ecx, eax
0x18000602c  movzx   eax, dl
0x18000602f  or      ecx, eax
0x180006031  mov     [rdi+rsi*4+2A0h], ecx
0x180006038  mov     rcx, [rsp+2F0h+Buffer]; pv
0x18000603d  call    cs:__imp_CoTaskMemFree
0x180006043  jmp     loc_180005F96
0x180006048  mov     rbx, [rsp+2F0h+Buffer]
0x18000604d  mov     rcx, rbx; unsigned __int16 *
0x180006050  call    ?HighContrastNumberFromSchemeName@@YAHPEBG@Z; HighContrastNumberFromSchemeName(ushort const *)
0x180006055  movsxd  rcx, eax
0x180006058  lea     rax, aSystemrootReso_4; "%SystemRoot%\\Resources\\Ease of Access"...
0x18000605f  mov     [rsp+2F0h+var_280], rax
0x180006064  lea     rax, aSystemrootReso_3; "%SystemRoot%\\Resources\\Ease of Access"...
0x18000606b  mov     [rsp+2F0h+var_278], rax
0x180006070  lea     rax, aSystemrootReso_5; "%SystemRoot%\\Resources\\Ease of Access"...
0x180006077  mov     [rbp+1F0h+var_270], rax
0x18000607b  lea     rax, aSystemrootReso_1; "%SystemRoot%\\Resources\\Ease of Access"...
0x180006082  mov     [rbp+1F0h+var_268], rax
0x180006086  test    ecx, ecx
0x180006088  jg      loc_1800061A7
0x18000608e  mov     r9d, 104h; cchBufferMax
0x180006094  lea     r8, [rbp+1F0h+String2]; lpBuffer
0x180006098  mov     edx, 7EBh; uID
0x18000609d  mov     rcx, cs:g_hinst; hInstance
0x1800060a4  call    cs:__imp_LoadStringW
0x1800060aa  test    eax, eax
0x1800060ac  jle     short loc_1800060D3
0x1800060ae  mov     [rsp+2F0h+bIgnoreCase], esi; bIgnoreCase
0x1800060b2  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800060b8  lea     r8, [rbp+1F0h+String2]; lpString2
0x1800060bc  mov     edx, r9d; cchCount1
0x1800060bf  mov     rcx, rbx; lpString1
0x1800060c2  call    cs:__imp_CompareStringOrdinal
0x1800060c8  movzx   r12d, r12b
0x1800060cc  cmp     eax, 2
0x1800060cf  cmovnz  r12d, esi
0x1800060d3  mov     rcx, rbx; pv
0x1800060d6  call    cs:__imp_CoTaskMemFree
0x1800060dc  jmp     loc_180005F46
0x1800060e1  mov     [rsp+2F0h+Buffer], 0
0x1800060ea  mov     [rsp+2F0h+var_2A0], 0
0x1800060f3  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x1800060f8  mov     edx, 2; unsigned __int64
0x1800060fd  mov     ecx, 0Bh; unsigned __int64
0x180006102  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180006107  mov     r14d, eax
0x18000610a  test    eax, eax
0x18000610c  js      short loc_180006120
0x18000610e  lea     r9, [rsp+2F0h+Buffer]; void **
0x180006113  mov     r8, [rsp+2F0h+var_2A0]; unsigned __int64
0x180006118  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000611d  mov     r14d, eax
0x180006120  test    r14d, r14d
0x180006123  js      loc_180005F93
0x180006129  mov     r9d, 0Ah; unsigned __int64
0x18000612f  lea     r8, a58110165; "58 110 165"
0x180006136  mov     edx, 0Bh; unsigned __int64
0x18000613b  mov     rcx, [rsp+2F0h+Buffer]; unsigned __int16 *
0x180006140  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180006145  jmp     loc_180005FCD
0x18000614a  mov     esi, 1
0x18000614f  mov     [rsp+2F0h+bIgnoreCase], esi; bIgnoreCase
0x180006153  mov     r9d, 0FFFFFFFFh; cchCount2
0x180006159  lea     r8, String2; "DABJDKT"
0x180006160  mov     edx, r9d; cchCount1
0x180006163  mov     rcx, [rsp+2F0h+bstrString]; lpString1
0x180006168  call    cs:__imp_CompareStringOrdinal
0x18000616e  cmp     eax, 2
0x180006171  jnz     loc_180005F46
0x180006177  lea     rax, [rsp+2F0h+Buffer]
0x18000617c  mov     qword ptr [rsp+2F0h+bIgnoreCase], rax; unsigned __int16 **
0x180006181  xor     r9d, r9d; unsigned int
0x180006184  lea     r8, aColorstyle; "ColorStyle"
0x18000618b  lea     rdx, aVisualstyles; "VisualStyles"
0x180006192  mov     rcx, rdi; this
0x180006195  call    ?_getThemeSetting@CThemeFile@@AEAAJPEBG0KPEAPEAG@Z; CThemeFile::_getThemeSetting(ushort const *,ushort const *,ulong,ushort * *)
0x18000619a  test    eax, eax
0x18000619c  js      loc_180005F46
0x1800061a2  jmp     loc_180006048
0x1800061a7  lea     eax, [rcx-1]
0x1800061aa  cmp     eax, 4
0x1800061ad  jnb     loc_18000608E
0x1800061b3  mov     r8d, 104h
0x1800061b9  lea     rdx, [rbp+1F0h+String2]
0x1800061bd  mov     rcx, [rsp+rcx*8+2F0h+var_288]
0x1800061c2  call    cs:__imp_SHExpandEnvironmentStringsW
0x1800061c8  test    eax, eax
0x1800061ca  jz      loc_1800060D3
0x1800061d0  lea     rdx, [rsp+2F0h+var_288]; struct ITheme **
0x1800061d5  lea     rcx, [rbp+1F0h+String2]; unsigned __int16 *
0x1800061d9  call    ?CThemeFile_CreateInstance@@YAJPEBGPEAPEAUITheme@@@Z; CThemeFile_CreateInstance(ushort const *,ITheme * *)
0x1800061de  jmp     loc_1800060D3
0x1800061e3  cmp     ebx, 1
0x1800061e6  jnz     loc_180005F93
0x1800061ec  jmp     loc_1800060E1
0x1800061f1  mov     eax, r14d
0x1800061f4  mov     ecx, r14d
0x1800061f7  mov     edx, r14d
0x1800061fa  jmp     loc_18000601E
```
