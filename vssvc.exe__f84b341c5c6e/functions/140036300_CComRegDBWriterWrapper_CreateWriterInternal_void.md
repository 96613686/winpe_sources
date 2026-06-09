# CComRegDBWriterWrapper::CreateWriterInternal(void)

- ea: `0x140036300`
- end: `0x140036782`
- name: `?CreateWriterInternal@CComRegDBWriterWrapper@@IEAAJXZ`
- size: `1154`
- prototype: `__int64 __fastcall(CComRegDBWriterWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14004f3e0`

## callees

- `0x1400137c0`
- `0x1400138e0`
- `0x1400139c0`
- `0x140013c60`
- `0x140036300`
- `0x1400921dc`
- `0x1400cfba8`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140036478`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140036478`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400365cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400365cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400363a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400364d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400363a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400364d7`
- `VssTrace!__imp_VssTraceMessage` at `0x14003672a`
- `VssTrace!__imp_VssTraceMessage` at `0x14003672a`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140036592`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140036660`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140036592`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140036660`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400363e1`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400363e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400364a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400364b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400364bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400364cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400365af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400364a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400364b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400364bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400364cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400365af`

## string_xrefs

- `0x14003632f`: `CComRegDBWriterWrapper::CreateWriterInternal`
- `0x140036682`: `CComRegDBWriterWrapper::CreateWriterInternal`
- `0x14003646e`: `CreateComRegDBWriter`
- `0x140036324`: `base\stor\vss\modules\writers\comregdbwriter.cxx`
- `0x1400366c8`: `CreateComRegDBWriter failed with hr 0x%08lx`
- `0x14003662a`: `catsrvut.dll could not be loaded.  No COM+ writer`
- `0x1400365c4`: `catsrvut.dll`
- `0x140036775`: `CreateComRegDBWriter could not be loaded.  No COM+ writer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CComRegDBWriterWrapper::CreateWriterInternal(CComRegDBWriterWrapper *this)
{
  struct CComRegDBWriterWrapper *v1; // rsi
  CComRegDBWriterWrapper *v2; // rax
  unsigned int v3; // r15d
  unsigned int v4; // ebx
  __int64 i; // rbx
  void *v6; // rcx
  HMODULE Library; // rdi
  __int64 (*ProcAddress)(void); // rax
  int v9; // r14d
  DWORD v10; // esi
  __int64 v12; // [rsp+20h] [rbp-E0h]
  __int64 v13; // [rsp+28h] [rbp-D8h]
  __int64 v14; // [rsp+30h] [rbp-D0h]
  __int64 v15; // [rsp+38h] [rbp-C8h]
  __int64 v16; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v17; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+58h] [rbp-A8h]
  const wchar_t *v19; // [rsp+60h] [rbp-A0h]
  const wchar_t *v20; // [rsp+68h] [rbp-98h]
  unsigned int v21; // [rsp+70h] [rbp-90h]
  unsigned int v22; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v23; // [rsp+78h] [rbp-88h]
  unsigned int v24; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  unsigned int v26; // [rsp+88h] [rbp-78h]
  LPVOID pv[2]; // [rsp+90h] [rbp-70h]
  LPVOID v28[2]; // [rsp+A0h] [rbp-60h]
  CComRegDBWriterWrapper *v29; // [rsp+B0h] [rbp-50h]
  const wchar_t *v30; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v31; // [rsp+C8h] [rbp-38h]
  const wchar_t *v32; // [rsp+D0h] [rbp-30h]
  int v33; // [rsp+D8h] [rbp-28h]
  int v34; // [rsp+DCh] [rbp-24h]
  int v35; // [rsp+E0h] [rbp-20h]
  LPVOID v36[15]; // [rsp+E8h] [rbp-18h] BYREF
  int v37; // [rsp+160h] [rbp+60h]
  CComRegDBWriterWrapper *v38; // [rsp+1C0h] [rbp+C0h] BYREF

  v38 = this;
  v1 = CComRegDBWriterWrapper::sm_pWriter;
  v30 = L"base\\stor\\vss\\modules\\writers\\comregdbwriter.cxx";
  v31 = L"CComRegDBWriterWrapper::CreateWriterInternal";
  v32 = L"WRTCDBRC";
  v33 = 48;
  v34 = 4;
  v35 = 255;
  v37 = 0x1000000;
  memset_0(v36, 0, sizeof(v36));
  v18 = 0;
  v23 = L"CComRegDBWriterWrapper::CreateWriterInternal";
  v19 = L"base\\stor\\vss\\modules\\writers\\comregdbwriter.cxx";
  v20 = L"WRTCDBRC";
  v21 = 48;
  v22 = 4;
  TickCount = GetTickCount();
  v26 = 255;
  v17 = 0xFFFFFFFF00000000uLL;
  v29 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v28 = 0;
  v38 = 0;
  if ( (int)VssGetTracingContextPerThread(&v38) < 0 || (int)VssSetTracingContextPerThread(&v17) < 0 )
  {
    v2 = v29;
  }
  else
  {
    v2 = v38;
    v29 = v38;
  }
  if ( v2 )
    v24 = *((_DWORD *)v2 + 12) + 1;
  else
    v24 = 0;
  v3 = 160;
  v4 = 160;
  if ( v26 != 255 )
    v4 = v26;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v17, v22) )
    VssTraceMessage(v19, v20, v21, v24, v22, v23, L"ENTER", v4, 0);
  if ( HIBYTE(v37) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v6 = v36[i];
      if ( v6 )
      {
        CoTaskMemFree(v6);
        v36[i] = 0;
      }
    }
  }
  if ( *((_BYTE *)v1 + 24) )
    goto LABEL_24;
  Library = (HMODULE)*((_QWORD *)v1 + 2);
  if ( !Library )
  {
    Library = LoadLibraryExW(L"catsrvut.dll", 0, 0);
    CVssAutoGenericValue_Storage<HINSTANCE__ *,0,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),HINSTANCE__ * & (*)(HINSTANCE__ * &),&public: static HINSTANCE__ * & DTyper<HINSTANCE__ *>::Identity(HINSTANCE__ * &)>::Close((char *)v1 + 8);
    *((_QWORD *)v1 + 2) = Library;
    if ( !Library )
    {
      v30 = L"base\\stor\\vss\\modules\\writers\\comregdbwriter.cxx";
      v31 = L"CComRegDBWriterWrapper::CreateWriterInternal";
      v32 = L"WRTCDBRC";
      v33 = 61;
      v34 = 4;
      v35 = 255;
      v37 = 0x1000000;
      memset_0(v36, 0, sizeof(v36));
      CVssFunctionTracer::Trace(&v17, &v30, L"catsrvut.dll could not be loaded.  No COM+ writer");
LABEL_24:
      v18 = 1;
      CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v17);
      return 1;
    }
  }
  ProcAddress = GetProcAddress(Library, "CreateComRegDBWriter");
  if ( !ProcAddress )
  {
    v30 = L"base\\stor\\vss\\modules\\writers\\comregdbwriter.cxx";
    v31 = L"CComRegDBWriterWrapper::CreateWriterInternal";
    v32 = L"WRTCDBRC";
    v33 = 70;
    v34 = 4;
    v35 = 255;
    v37 = 0x1000000;
    memset_0(v36, 0, sizeof(v36));
    CVssFunctionTracer::Trace(&v17, &v30, L"CreateComRegDBWriter could not be loaded.  No COM+ writer");
    goto LABEL_24;
  }
  v9 = ProcAddress();
  v18 = v9;
  if ( v9 < 0 )
  {
    v30 = L"base\\stor\\vss\\modules\\writers\\comregdbwriter.cxx";
    v31 = L"CComRegDBWriterWrapper::CreateWriterInternal";
    v32 = L"WRTCDBRC";
    v33 = 77;
    v34 = 4;
    v35 = 255;
    v37 = 0x1000000;
    memset_0(v36, 0, sizeof(v36));
    CVssFunctionTracer::Trace(&v17, &v30, L"CreateComRegDBWriter failed with hr 0x%08lx", (unsigned int)v9);
    v9 = v18;
  }
  else
  {
    *((_BYTE *)v1 + 24) = 1;
  }
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v28[0]);
  v28[0] = 0;
  CoTaskMemFree(v28[1]);
  v28[1] = 0;
  v10 = GetTickCount() - TickCount;
  if ( v26 != 255 )
    v3 = v26;
  LODWORD(v16) = v10;
  LODWORD(v15) = v10 % 0x3E8;
  LODWORD(v14) = v10 / 0x3E8 % 0x3C;
  LODWORD(v13) = v10 / 0xEA60 % 0x3C;
  LODWORD(v12) = v10 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)&v17,
    L"EXIT",
    v3,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v12,
    v13,
    v14,
    v15,
    v16,
    v18);
  VssSetTracingContextPerThread(v29);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140036300  mov     [rsp-8+arg_0], rcx
0x140036305  push    rbp
0x140036306  push    rbx
0x140036307  push    rsi
0x140036308  push    rdi
0x140036309  push    r12
0x14003630b  push    r13
0x14003630d  push    r14
0x14003630f  push    r15
0x140036311  lea     rbp, [rsp-78h]
0x140036316  sub     rsp, 178h
0x14003631d  mov     rsi, cs:?sm_pWriter@CComRegDBWriterWrapper@@0PEAV1@EA; CComRegDBWriterWrapper * CComRegDBWriterWrapper::sm_pWriter
0x140036324  lea     r13, aBaseStorVssMod_0; "base\\stor\\vss\\modules\\writers\\comr"...
0x14003632b  mov     [rbp+0B0h+var_F0], r13
0x14003632f  lea     r14, aCcomregdbwrite_0; "CComRegDBWriterWrapper::CreateWriterInt"...
0x140036336  mov     [rbp+0B0h+var_E8], r14
0x14003633a  lea     rax, aWrtcdbrc; "WRTCDBRC"
0x140036341  mov     [rbp+0B0h+var_E0], rax
0x140036345  mov     [rbp+0B0h+var_D8], 30h ; '0'
0x14003634c  mov     [rbp+0B0h+var_D4], 4
0x140036353  mov     [rbp+0B0h+var_D0], 0FFh
0x14003635a  xor     r12d, r12d
0x14003635d  mov     [rbp+0B0h+var_50], 1000000h
0x140036364  xor     edx, edx; Val
0x140036366  mov     r8d, 78h ; 'x'; Size
0x14003636c  lea     rcx, [rbp+0B0h+var_C8]; void *
0x140036370  call    memset_0
0x140036375  mov     [rsp+1B0h+var_158], r12d
0x14003637a  mov     rax, [rbp+0B0h+var_E8]
0x14003637e  mov     [rsp+1B0h+var_138], rax
0x140036383  mov     rax, [rbp+0B0h+var_F0]
0x140036387  mov     [rsp+1B0h+var_150], rax
0x14003638c  mov     rax, [rbp+0B0h+var_E0]
0x140036390  mov     [rsp+1B0h+var_148], rax
0x140036395  mov     eax, [rbp+0B0h+var_D8]
0x140036398  mov     [rsp+1B0h+var_140], eax
0x14003639c  mov     eax, [rbp+0B0h+var_D4]
0x14003639f  mov     [rsp+1B0h+var_13C], eax
0x1400363a3  call    cs:__imp_GetTickCount
0x1400363a9  mov     [rbp+0B0h+var_12C], eax
0x1400363ac  mov     [rsp+1B0h+var_15C], 0FFFFFFFFh
0x1400363b4  mov     eax, [rbp+0B0h+var_D0]
0x1400363b7  mov     [rbp+0B0h+var_128], eax
0x1400363ba  mov     [rsp+1B0h+var_160], r12d
0x1400363bf  mov     [rbp+0B0h+var_100], r12
0x1400363c3  xorps   xmm0, xmm0
0x1400363c6  movdqa  xmmword ptr [rbp+0B0h+pv], xmm0
0x1400363cb  xorps   xmm1, xmm1
0x1400363ce  movdqa  xmmword ptr [rbp+0B0h+var_110], xmm1
0x1400363d3  mov     [rbp+0B0h+arg_0], r12
0x1400363da  lea     rcx, [rbp+0B0h+arg_0]
0x1400363e1  call    cs:__imp_VssGetTracingContextPerThread
0x1400363e7  test    eax, eax
0x1400363e9  jns     loc_14003665B
0x1400363ef  mov     rax, [rbp+0B0h+var_100]
0x1400363f3  test    rax, rax
0x1400363f6  jz      loc_1400366E7
0x1400363fc  mov     eax, [rax+30h]
0x1400363ff  inc     eax
0x140036401  mov     [rbp+0B0h+var_130], eax
0x140036404  mov     r15d, 0A0h
0x14003640a  mov     ebx, r15d
0x14003640d  cmp     [rbp+0B0h+var_128], 0FFh
0x140036414  cmovnz  ebx, [rbp+0B0h+var_128]
0x140036418  mov     edx, [rsp+1B0h+var_13C]; unsigned int
0x14003641c  lea     rcx, [rsp+1B0h+var_160]; this
0x140036421  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140036426  test    eax, eax
0x140036428  jnz     loc_1400366F0
0x14003642e  cmp     byte ptr [rbp+0B0h+var_50+3], r12b
0x140036432  jz      short loc_140036457
0x140036434  mov     rbx, r12
0x140036437  nop     word ptr [rax+rax+00000000h]
0x140036440  mov     rcx, [rbp+rbx*8+0B0h+var_C8]; pv
0x140036445  test    rcx, rcx
0x140036448  jnz     loc_1400365AF
0x14003644e  inc     rbx
0x140036451  cmp     rbx, 0Fh
0x140036455  jnz     short loc_140036440
0x140036457  cmp     byte ptr [rsi+18h], 0
0x14003645b  jnz     loc_14003663F
0x140036461  mov     rdi, [rsi+10h]
0x140036465  test    rdi, rdi
0x140036468  jz      loc_1400365BF
0x14003646e  lea     rdx, ProcName; "CreateComRegDBWriter"
0x140036475  mov     rcx, rdi; hModule
0x140036478  call    cs:__imp_GetProcAddress
0x14003647e  test    rax, rax
0x140036481  jz      loc_140036735
0x140036487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003648c  mov     r14d, eax
0x14003648f  mov     [rsp+1B0h+var_158], eax
0x140036493  test    eax, eax
0x140036495  js      loc_14003667E
0x14003649b  mov     byte ptr [rsi+18h], 1
0x14003649f  mov     rcx, [rbp+0B0h+pv]; pv
0x1400364a3  call    cs:__imp_CoTaskMemFree
0x1400364a9  mov     [rbp+0B0h+pv], r12
0x1400364ad  mov     rcx, [rbp+0B0h+pv+8]; pv
0x1400364b1  call    cs:__imp_CoTaskMemFree
0x1400364b7  mov     [rbp+0B0h+pv+8], r12
0x1400364bb  mov     rcx, [rbp+0B0h+var_110]; pv
0x1400364bf  call    cs:__imp_CoTaskMemFree
0x1400364c5  mov     [rbp+0B0h+var_110], r12
0x1400364c9  mov     rcx, [rbp+0B0h+var_110+8]; pv
0x1400364cd  call    cs:__imp_CoTaskMemFree
0x1400364d3  mov     [rbp+0B0h+var_110+8], r12
0x1400364d7  call    cs:__imp_GetTickCount
0x1400364dd  mov     esi, eax
0x1400364df  sub     esi, [rbp+0B0h+var_12C]
0x1400364e2  mov     eax, 10624DD3h
0x1400364e7  mul     esi
0x1400364e9  mov     edi, edx
0x1400364eb  shr     edi, 6
0x1400364ee  mov     eax, 88888889h
0x1400364f3  mul     edi
0x1400364f5  shr     edx, 5
0x1400364f8  imul    ecx, edx, 3Ch ; '<'
0x1400364fb  mov     ebx, edi
0x1400364fd  sub     ebx, ecx
0x1400364ff  mov     eax, 45E7B273h
0x140036504  mul     esi
0x140036506  mov     r11d, edx
0x140036509  shr     r11d, 0Eh
0x14003650d  mov     eax, 88888889h
0x140036512  mul     r11d
0x140036515  shr     edx, 5
0x140036518  imul    ecx, edx, 3Ch ; '<'
0x14003651b  sub     r11d, ecx
0x14003651e  mov     eax, 95217CB1h
0x140036523  mul     esi
0x140036525  mov     r10d, edx
0x140036528  shr     r10d, 15h
0x14003652c  mov     eax, 88888889h
0x140036531  mul     r10d
0x140036534  shr     edx, 5
0x140036537  imul    eax, edx, 3Ch ; '<'
0x14003653a  sub     r10d, eax
0x14003653d  mov     r9d, [rsp+1B0h+var_158]
0x140036542  cmp     [rbp+0B0h+var_128], 0FFh
0x140036549  cmovnz  r15d, [rbp+0B0h+var_128]
0x14003654e  imul    ecx, edi, 3E8h
0x140036554  mov     edx, esi
0x140036556  sub     edx, ecx
0x140036558  mov     [rsp+1B0h+var_168], r9d
0x14003655d  mov     dword ptr [rsp+1B0h+var_170], esi
0x140036561  mov     dword ptr [rsp+1B0h+var_178], edx
0x140036565  mov     dword ptr [rsp+1B0h+var_180], ebx
0x140036569  mov     dword ptr [rsp+1B0h+var_188], r11d
0x14003656e  mov     dword ptr [rsp+1B0h+var_190], r10d
0x140036573  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x14003657a  mov     r8d, r15d; unsigned int
0x14003657d  lea     rdx, aExit; "EXIT"
0x140036584  lea     rcx, [rsp+1B0h+var_160]; this
0x140036589  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14003658e  mov     rcx, [rbp+0B0h+var_100]
0x140036592  call    cs:__imp_VssSetTracingContextPerThread
0x140036598  mov     eax, r14d
0x14003659b  add     rsp, 178h
0x1400365a2  pop     r15
0x1400365a4  pop     r14
0x1400365a6  pop     r13
0x1400365a8  pop     r12
0x1400365aa  pop     rdi
0x1400365ab  pop     rsi
0x1400365ac  pop     rbx
0x1400365ad  pop     rbp
0x1400365ae  retn
0x1400365af  call    cs:__imp_CoTaskMemFree
0x1400365b5  mov     [rbp+rbx*8+0B0h+var_C8], r12
0x1400365ba  jmp     loc_14003644E
0x1400365bf  xor     r8d, r8d; dwFlags
0x1400365c2  xor     edx, edx; hFile
0x1400365c4  lea     rcx, aCatsrvutDll; "catsrvut.dll"
0x1400365cb  call    cs:__imp_LoadLibraryExW
0x1400365d1  mov     rdi, rax
0x1400365d4  lea     rcx, [rsi+8]
0x1400365d8  call    ?Close@?$CVssAutoGenericValue_Storage@PEAUHINSTANCE__@@$0A@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHINSTANCE__@@@@SAAEAPEAU1@1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<HINSTANCE__ *,0,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),HINSTANCE__ * & (*)(HINSTANCE__ * &),&DTyper<HINSTANCE__ *>::Identity(HINSTANCE__ * &)>::Close(void)
0x1400365dd  mov     [rsi+10h], rdi
0x1400365e1  test    rdi, rdi
0x1400365e4  jnz     loc_14003646E
0x1400365ea  mov     [rbp+0B0h+var_F0], r13
0x1400365ee  mov     [rbp+0B0h+var_E8], r14
0x1400365f2  lea     rax, aWrtcdbrc; "WRTCDBRC"
0x1400365f9  mov     [rbp+0B0h+var_E0], rax
0x1400365fd  mov     [rbp+0B0h+var_D8], 3Dh ; '='
0x140036604  mov     [rbp+0B0h+var_D4], 4
0x14003660b  mov     [rbp+0B0h+var_D0], 0FFh
0x140036612  mov     [rbp+0B0h+var_50], 1000000h
0x140036619  xor     edx, edx; Val
0x14003661b  mov     r8d, 78h ; 'x'; Size
0x140036621  lea     rcx, [rbp+0B0h+var_C8]; void *
0x140036625  call    memset_0
0x14003662a  lea     r8, aCatsrvutDllCou; "catsrvut.dll could not be loaded.  No C"...
0x140036631  lea     rdx, [rbp+0B0h+var_F0]
0x140036635  lea     rcx, [rsp+1B0h+var_160]
0x14003663a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14003663f  mov     [rsp+1B0h+var_158], 1
0x140036647  lea     rcx, [rsp+1B0h+var_160]; this
0x14003664c  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140036651  mov     eax, 1
0x140036656  jmp     loc_14003659B
0x14003665b  lea     rcx, [rsp+1B0h+var_160]
0x140036660  call    cs:__imp_VssSetTracingContextPerThread
0x140036666  test    eax, eax
0x140036668  js      loc_1400363EF
0x14003666e  mov     rax, [rbp+0B0h+arg_0]
0x140036675  mov     [rbp+0B0h+var_100], rax
0x140036679  jmp     loc_1400363F3
0x14003667e  mov     [rbp+0B0h+var_F0], r13
0x140036682  lea     rax, aCcomregdbwrite_0; "CComRegDBWriterWrapper::CreateWriterInt"...
0x140036689  mov     [rbp+0B0h+var_E8], rax
0x14003668d  lea     rax, aWrtcdbrc; "WRTCDBRC"
0x140036694  mov     [rbp+0B0h+var_E0], rax
0x140036698  mov     [rbp+0B0h+var_D8], 4Dh ; 'M'
0x14003669f  mov     [rbp+0B0h+var_D4], 4
0x1400366a6  mov     [rbp+0B0h+var_D0], 0FFh
0x1400366ad  mov     [rbp+0B0h+var_50], 1000000h
0x1400366b4  xor     edx, edx; Val
0x1400366b6  mov     r8d, 78h ; 'x'; Size
0x1400366bc  lea     rcx, [rbp+0B0h+var_C8]; void *
0x1400366c0  call    memset_0
0x1400366c5  mov     r9d, r14d
0x1400366c8  lea     r8, aCreatecomregdb_1; "CreateComRegDBWriter failed with hr 0x%"...
0x1400366cf  lea     rdx, [rbp+0B0h+var_F0]
0x1400366d3  lea     rcx, [rsp+1B0h+var_160]
0x1400366d8  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400366dd  mov     r14d, [rsp+1B0h+var_158]
0x1400366e2  jmp     loc_14003649F
0x1400366e7  mov     [rbp+0B0h+var_130], r12d
0x1400366eb  jmp     loc_140036404
0x1400366f0  mov     [rsp+1B0h+var_170], r12
0x1400366f5  mov     dword ptr [rsp+1B0h+var_178], ebx
0x1400366f9  lea     rax, aEnter; "ENTER"
0x140036700  mov     [rsp+1B0h+var_180], rax
0x140036705  mov     rax, [rsp+1B0h+var_138]
0x14003670a  mov     [rsp+1B0h+var_188], rax
0x14003670f  mov     eax, [rsp+1B0h+var_13C]
0x140036713  mov     dword ptr [rsp+1B0h+var_190], eax
0x140036717  mov     r9d, [rbp+0B0h+var_130]
0x14003671b  mov     r8d, [rsp+1B0h+var_140]
0x140036720  mov     rdx, [rsp+1B0h+var_148]
0x140036725  mov     rcx, [rsp+1B0h+var_150]
0x14003672a  call    cs:__imp_VssTraceMessage
0x140036730  jmp     loc_14003642E
0x140036735  mov     [rbp+0B0h+var_F0], r13
0x140036739  mov     [rbp+0B0h+var_E8], r14
0x14003673d  lea     rax, aWrtcdbrc; "WRTCDBRC"
0x140036744  mov     [rbp+0B0h+var_E0], rax
0x140036748  mov     [rbp+0B0h+var_D8], 46h ; 'F'
0x14003674f  mov     [rbp+0B0h+var_D4], 4
0x140036756  mov     [rbp+0B0h+var_D0], 0FFh
0x14003675d  mov     [rbp+0B0h+var_50], 1000000h
0x140036764  xor     edx, edx; Val
0x140036766  mov     r8d, 78h ; 'x'; Size
0x14003676c  lea     rcx, [rbp+0B0h+var_C8]; void *
0x140036770  call    memset_0
0x140036775  lea     r8, aCreatecomregdb_0; "CreateComRegDBWriter could not be loade"...
0x14003677c  jmp     loc_140036631
```
