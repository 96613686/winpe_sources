# CHost::Main(HINSTANCE__ *,int,ushort const * *,IMoniker *)

- ea: `0x14000919c`
- end: `0x1400097dd`
- name: `?Main@CHost@@QEAAHPEAUHINSTANCE__@@HPEAPEBGPEAUIMoniker@@@Z`
- size: `1601`
- prototype: `__int64 __usercall@<rax>(CHost *__hidden this@<rcx>, HINSTANCE@<rdx>, int@<r8d>, const unsigned __int16 **@<r9>, struct IMoniker *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x140002310`
- `0x140006c88`

## callees

- `0x140001008`
- `0x14000757c`
- `0x140008994`
- `0x140008eb0`
- `0x14000919c`
- `0x14000a3f8`
- `0x140010d64`
- `0x140010e30`
- `0x14001108c`
- `0x1400111d0`
- `0x1400175a0`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140009271`
- `KERNEL32!GetProcAddress` at `0x140009271`
- `KERNEL32!GetModuleFileNameA` at `0x14000936b`
- `KERNEL32!GetModuleFileNameA` at `0x14000936b`
- `KERNEL32!MultiByteToWideChar` at `0x1400093a6`
- `KERNEL32!MultiByteToWideChar` at `0x1400093a6`
- `KERNEL32!GetModuleFileNameW` at `0x14000933f`
- `KERNEL32!GetModuleFileNameW` at `0x14000933f`
- `KERNEL32!GetACP` at `0x1400091ea`
- `KERNEL32!GetACP` at `0x140009547`
- `KERNEL32!GetACP` at `0x1400091ea`
- `KERNEL32!GetACP` at `0x140009547`
- `KERNEL32!FreeLibrary` at `0x14000927f`
- `KERNEL32!FreeLibrary` at `0x1400092ca`
- `KERNEL32!FreeLibrary` at `0x14000927f`
- `KERNEL32!FreeLibrary` at `0x1400092ca`
- `KERNEL32!LoadLibraryExW` at `0x140009259`
- `KERNEL32!LoadLibraryExW` at `0x140009259`
- `ole32!CoRegisterMessageFilter` at `0x14000930c`
- `ole32!CoRegisterMessageFilter` at `0x14000930c`

## string_xrefs

- `0x14000924c`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall CHost::Main(CHost *this, HINSTANCE a2, int a3, const unsigned __int16 **a4, struct IMoniker *a5)
{
  unsigned int v8; // esi
  HMODULE Library; // rax
  HMODULE v10; // r14
  FARPROC ProcAddress; // rax
  int v13; // ebx
  void *v14; // rbx
  HMODULE v15; // rcx
  const WCHAR *v16; // rbx
  int ModuleVersion; // eax
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // r8
  int v21; // eax
  int v22; // eax
  HKEY v23; // rdx
  __int64 v24; // r8
  char v25; // cl
  char v26; // al
  UINT v27; // eax
  HKEY v28; // rdx
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // r10
  CHost *v34; // rcx
  __int64 v35; // r8
  void (__fastcall *v36)(CHost *, __int64, __int64); // rax
  __int64 v37; // rdx
  char v38; // al
  int v39; // eax
  __int64 v40; // r8
  int v41; // r9d
  int i; // ebx
  int v43; // r9d
  unsigned int v44; // ebx
  int v45; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v46; // [rsp+44h] [rbp-BCh]
  char v47; // [rsp+46h] [rbp-BAh]
  __int16 v48; // [rsp+47h] [rbp-B9h]
  UINT ACP; // [rsp+4Ch] [rbp-B4h]
  __int64 v50; // [rsp+50h] [rbp-B0h]
  unsigned int v51; // [rsp+58h] [rbp-A8h]
  WCHAR WideCharStr[260]; // [rsp+5Ch] [rbp-A4h] BYREF
  int v53; // [rsp+264h] [rbp+164h]
  const unsigned __int16 **v54; // [rsp+268h] [rbp+168h]
  int v55; // [rsp+270h] [rbp+170h]
  unsigned __int16 *v56; // [rsp+278h] [rbp+178h]
  __int64 v57; // [rsp+280h] [rbp+180h] BYREF
  __int64 v58; // [rsp+288h] [rbp+188h]
  CHAR Filename[4]; // [rsp+290h] [rbp+190h] BYREF
  char v60; // [rsp+294h] [rbp+194h]
  int v61; // [rsp+295h] [rbp+195h]
  UINT v62; // [rsp+29Ch] [rbp+19Ch]
  __int64 v63; // [rsp+2A0h] [rbp+1A0h]
  int v64; // [rsp+2A8h] [rbp+1A8h]
  __int16 v65; // [rsp+2ACh] [rbp+1ACh]
  char v66; // [rsp+394h] [rbp+294h]

  v45 = 0;
  v8 = 1;
  v47 = 1;
  ACP = GetACP();
  v50 = 0;
  v51 = 87;
  WideCharStr[0] = 0;
  v46 = 0;
  v48 = 0;
  v57 = 0;
  v58 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  if ( Global::g_fWindowsVista )
  {
    Library = LoadLibraryExW(L"kernel32.dll", 0, 0x800u);
    v10 = Library;
    if ( !Library )
    {
LABEL_5:
      JobList::~JobList((JobList *)&v57);
      return v8;
    }
    ProcAddress = GetProcAddress(Library, "HeapSetInformation");
    if ( !ProcAddress )
    {
      FreeLibrary(v10);
      goto LABEL_5;
    }
    v13 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))ProcAddress)(0, 1, 0, 0);
    FreeLibrary(v10);
    if ( !v13 )
      goto LABEL_5;
  }
  v14 = operator new(0x20u);
  if ( v14 )
  {
    *((_BYTE *)v14 + 8) = 0;
    *(_QWORD *)v14 = &CMessageFilter::`vftable';
    *((_QWORD *)v14 + 2) = 0;
    *((_DWORD *)v14 + 6) = 1;
    *((_QWORD *)this + 86) = v14;
    if ( CoRegisterMessageFilter((LPMESSAGEFILTER)v14, (LPMESSAGEFILTER *)v14 + 2) >= 0 )
      *((_BYTE *)v14 + 8) = 1;
  }
  v15 = Global::g_hInstance;
  if ( Global::g_fWindowsNT )
  {
    v16 = (const WCHAR *)((char *)this + 80);
    *((_WORD *)this + 300) = 0;
    if ( !GetModuleFileNameW(v15, (LPWSTR)this + 40, 0x105u) || *((_WORD *)this + 300) )
      goto LABEL_5;
  }
  else
  {
    v66 = 0;
    if ( !GetModuleFileNameA(Global::g_hInstance, Filename, 0x105u) )
      goto LABEL_5;
    if ( v66 )
      goto LABEL_5;
    v16 = (const WCHAR *)((char *)this + 80);
    if ( !MultiByteToWideChar(0, 0, Filename, -1, (LPWSTR)this + 40, 261) )
      goto LABEL_5;
  }
  ModuleVersion = GetModuleVersion(v16);
  if ( ModuleVersion < 0 )
  {
    (**(void (__fastcall ***)(CHost *, _QWORD, __int64, _QWORD))this)(
      this,
      (unsigned int)(Global::g_lResourceBase + 20),
      3200,
      (unsigned int)ModuleVersion);
    goto LABEL_5;
  }
  CHost::GetTrustPolicyFromRegistry(this);
  if ( a3 == 1 )
  {
    v8 = (*(__int64 (__fastcall **)(CHost *))(*(_QWORD *)this + 56LL))(this);
    goto LABEL_5;
  }
  v53 = a3 - 1;
  v54 = a4 + 1;
  v18 = CSettings::LoadFromRegistry((CSettings *)&v45, HKEY_LOCAL_MACHINE);
  v19 = (unsigned int)v18;
  if ( v18 < 0
    || (v21 = CSettings::LoadFromRegistry((CSettings *)&v45, HKEY_CURRENT_USER), v19 = (unsigned int)v21, v21 < 0) )
  {
    v20 = 3205;
    goto LABEL_27;
  }
  *((_BYTE *)this + 68) = BYTE1(v50);
  v22 = CCmdLineArgs::Parse((CCmdLineArgs *)&v45);
  v19 = (unsigned int)v22;
  if ( v22 < 0 )
  {
    if ( v22 == -2147155969 )
      goto LABEL_5;
    v20 = 3207;
LABEL_27:
    (**(void (__fastcall ***)(CHost *, _QWORD, __int64, __int64))this)(
      this,
      (unsigned int)(Global::g_lResourceBase + 20),
      v20,
      v19);
    goto LABEL_5;
  }
  v25 = BYTE5(v50);
  *((_BYTE *)this + 68) = BYTE1(v50);
  *((_DWORD *)this + 11) = v45;
  *((_BYTE *)this + 69) = v46;
  *((_BYTE *)this + 71) = BYTE3(v50);
  *((_BYTE *)this + 73) = HIBYTE(v50);
  *((_BYTE *)this + 72) = v25;
  if ( v25 && BYTE6(v50) )
    *((_BYTE *)this + 71) = 1;
  v26 = *((_BYTE *)this + 75);
  if ( v26 )
    *((_BYTE *)this + 68) = 1;
  if ( BYTE2(v55) )
  {
    if ( !v26 )
    {
      *((_BYTE *)this + 68) = 0;
      if ( v47 )
        (*(void (__fastcall **)(CHost *, HKEY, __int64, __int64))(*(_QWORD *)this + 16LL))(this, v23, v24, v19);
      (*(void (__fastcall **)(CHost *, HKEY, __int64, __int64))(*(_QWORD *)this + 24LL))(this, v23, v24, v19);
    }
    goto LABEL_47;
  }
  if ( v47 )
    (*(void (__fastcall **)(CHost *, HKEY, __int64, __int64))(*(_QWORD *)this + 16LL))(this, v23, v24, v19);
  if ( BYTE1(v55) )
  {
    *(_DWORD *)Filename = 0;
    v61 = 256;
    v27 = GetACP();
    v63 = 0;
    v62 = v27;
    v64 = 87;
    v65 = 0;
    v60 = 0;
    v29 = CSettings::SaveToRegistry((CSettings *)Filename, v28);
    if ( v29 >= 0 )
      v29 = ChangeDefaultHost(87, v30, v31, v32);
    v33 = *(_QWORD *)this;
    v34 = this;
    if ( v29 < 0 )
      goto LABEL_45;
    (*(void (__fastcall **)(CHost *, _QWORD, __int64))(v33 + 32))(this, 0, 3050);
LABEL_47:
    v8 = 0;
    goto LABEL_5;
  }
  v38 = 0;
  if ( (_BYTE)v55 )
  {
    v39 = CSettings::SaveToRegistry((CSettings *)&v45, v23);
    v33 = *(_QWORD *)this;
    v34 = this;
    if ( v39 < 0 )
    {
LABEL_45:
      v35 = 3203;
      v36 = *(void (__fastcall **)(CHost *, __int64, __int64))(v33 + 8);
      v37 = (unsigned int)(Global::g_lResourceBase + 20);
LABEL_67:
      v36(v34, v37, v35);
      goto LABEL_5;
    }
    (*(void (__fastcall **)(CHost *, _QWORD, __int64))(v33 + 32))(this, 0, 3051);
    v38 = 1;
  }
  if ( HIBYTE(v55) )
  {
    if ( (int)ChangeDefaultHost(v51, v23, v24, v19) < 0 )
    {
      v35 = 3202;
      v37 = (unsigned int)(Global::g_lResourceBase + 20);
LABEL_66:
      v34 = this;
      v36 = *(void (__fastcall **)(CHost *, __int64, __int64))(*(_QWORD *)this + 8LL);
      goto LABEL_67;
    }
    if ( !v53 )
    {
      if ( v51 == 67 )
      {
        v40 = 3053;
      }
      else
      {
        if ( v51 != 87 )
          goto LABEL_5;
        v40 = 3052;
      }
      (*(void (__fastcall **)(CHost *, _QWORD, __int64))(*(_QWORD *)this + 32LL))(this, 0, v40);
    }
    v38 = 1;
  }
  if ( !v53 )
  {
    if ( v38 )
      goto LABEL_47;
    goto LABEL_65;
  }
  if ( !WideCharStr[0] )
  {
LABEL_65:
    v35 = 3304;
    v37 = (unsigned int)(Global::g_lResourceBase + 21);
    goto LABEL_66;
  }
  if ( (_DWORD)v58 )
  {
    for ( i = 0; i < (int)v58; ++i )
    {
      v43 = CHost::Execute(this, WideCharStr, v53 - 1, v54 + 1, v56, *(unsigned __int16 **)(v57 + 8LL * i), a5);
      if ( v43 < 0 )
      {
        if ( !*((_BYTE *)this + 70) )
          *((_DWORD *)this + 16) = 1;
        if ( v43 != -2147155969 )
          (**(void (__fastcall ***)(CHost *, _QWORD, __int64))this)(
            this,
            (unsigned int)(Global::g_lResourceBase + 20),
            3207);
      }
    }
  }
  else
  {
    v41 = CHost::Execute(this, WideCharStr, v53 - 1, v54 + 1, v56, 0, a5);
    if ( v41 < 0 )
    {
      if ( !*((_BYTE *)this + 70) )
        *((_DWORD *)this + 16) = 1;
      if ( v41 != -2147155969 )
        (**(void (__fastcall ***)(CHost *, _QWORD, __int64))this)(
          this,
          (unsigned int)(Global::g_lResourceBase + 20),
          3207);
    }
  }
  v44 = *((_DWORD *)this + 16);
  JobList::~JobList((JobList *)&v57);
  return v44;
}

```

## disassembly

```asm
0x14000919c  push    rbp
0x14000919e  push    rbx
0x14000919f  push    rsi
0x1400091a0  push    rdi
0x1400091a1  push    r12
0x1400091a3  push    r13
0x1400091a5  push    r14
0x1400091a7  push    r15
0x1400091a9  lea     rbp, [rsp-3D8h]
0x1400091b1  sub     rsp, 4D8h
0x1400091b8  mov     rax, cs:__security_cookie
0x1400091bf  xor     rax, rsp
0x1400091c2  mov     [rbp+410h+var_50], rax
0x1400091c9  mov     r12, [rbp+410h+arg_20]
0x1400091d0  xor     r14d, r14d
0x1400091d3  mov     r13, r9
0x1400091d6  mov     [rsp+510h+var_4D0], r14d
0x1400091db  mov     r15d, r8d
0x1400091de  mov     rdi, rcx
0x1400091e1  lea     esi, [r14+1]
0x1400091e5  mov     [rsp+510h+var_4CA], sil
0x1400091ea  call    cs:__imp_GetACP
0x1400091f0  cmp     cs:?g_fWindowsVista@Global@@2_NA, r14b; bool Global::g_fWindowsVista
0x1400091f7  mov     [rsp+510h+var_4C4], eax
0x1400091fb  mov     [rsp+510h+var_4C0], r14
0x140009200  mov     [rsp+510h+var_4B8], 57h ; 'W'
0x140009208  mov     [rsp+510h+WideCharStr], r14w
0x14000920e  mov     [rsp+510h+var_4CC], r14w
0x140009214  mov     [rsp+510h+var_4C9], r14w
0x14000921a  mov     [rbp+410h+var_290], r14
0x140009221  mov     [rbp+410h+var_288], r14
0x140009228  mov     [rbp+410h+var_2AC], r14d
0x14000922f  mov     [rbp+410h+var_2A8], r14
0x140009236  mov     [rbp+410h+var_2A0], r14d
0x14000923d  mov     [rbp+410h+var_298], r14
0x140009244  jz      loc_1400092D7
0x14000924a  xor     edx, edx; hFile
0x14000924c  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x140009253  mov     r8d, 800h; dwFlags
0x140009259  call    cs:__imp_LoadLibraryExW
0x14000925f  mov     r14, rax
0x140009262  test    rax, rax
0x140009265  jz      short loc_140009285
0x140009267  lea     rdx, aHeapsetinforma; "HeapSetInformation"
0x14000926e  mov     rcx, rax; hModule
0x140009271  call    cs:__imp_GetProcAddress
0x140009277  test    rax, rax
0x14000927a  jnz     short loc_1400092B6
0x14000927c  mov     rcx, r14; hLibModule
0x14000927f  call    cs:__imp_FreeLibrary
0x140009285  lea     rcx, [rbp+410h+var_290]; this
0x14000928c  call    ??1JobList@@QEAA@XZ; JobList::~JobList(void)
0x140009291  mov     eax, esi
0x140009293  mov     rcx, [rbp+410h+var_50]
0x14000929a  xor     rcx, rsp; StackCookie
0x14000929d  call    __security_check_cookie
0x1400092a2  add     rsp, 4D8h
0x1400092a9  pop     r15
0x1400092ab  pop     r14
0x1400092ad  pop     r13
0x1400092af  pop     r12
0x1400092b1  pop     rdi
0x1400092b2  pop     rsi
0x1400092b3  pop     rbx
0x1400092b4  pop     rbp
0x1400092b5  retn
0x1400092b6  xor     r9d, r9d
0x1400092b9  xor     r8d, r8d
0x1400092bc  mov     edx, esi
0x1400092be  xor     ecx, ecx
0x1400092c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092c5  mov     rcx, r14; hLibModule
0x1400092c8  mov     ebx, eax
0x1400092ca  call    cs:__imp_FreeLibrary
0x1400092d0  xor     r14d, r14d
0x1400092d3  test    ebx, ebx
0x1400092d5  jz      short loc_140009285
0x1400092d7  mov     ecx, 20h ; ' '; Size
0x1400092dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400092e1  mov     rbx, rax
0x1400092e4  test    rax, rax
0x1400092e7  jz      short loc_14000931A
0x1400092e9  lea     rax, ??_7CMessageFilter@@6B@; const CMessageFilter::`vftable'
0x1400092f0  mov     [rbx+8], r14b
0x1400092f4  mov     [rbx], rax
0x1400092f7  lea     rdx, [rbx+10h]; lplpMessageFilter
0x1400092fb  mov     [rbx+10h], r14
0x1400092ff  mov     rcx, rbx; lpMessageFilter
0x140009302  mov     [rbx+18h], esi
0x140009305  mov     [rdi+2B0h], rbx
0x14000930c  call    cs:__imp_CoRegisterMessageFilter
0x140009312  test    eax, eax
0x140009314  js      short loc_14000931A
0x140009316  mov     [rbx+8], sil
0x14000931a  cmp     cs:?g_fWindowsNT@Global@@2_NA, r14b; bool Global::g_fWindowsNT
0x140009321  mov     r8d, 105h; nSize
0x140009327  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hModule
0x14000932e  jz      short loc_14000935D
0x140009330  lea     rbx, [rdi+50h]
0x140009334  mov     [rdi+258h], r14w
0x14000933c  mov     rdx, rbx; lpFilename
0x14000933f  call    cs:__imp_GetModuleFileNameW
0x140009345  test    eax, eax
0x140009347  jz      loc_140009285
0x14000934d  cmp     r14w, [rdi+258h]
0x140009355  jnz     loc_140009285
0x14000935b  jmp     short loc_1400093B4
0x14000935d  lea     rdx, [rbp+410h+Filename]; lpFilename
0x140009364  mov     [rbp+410h+var_17C], r14b
0x14000936b  call    cs:__imp_GetModuleFileNameA
0x140009371  test    eax, eax
0x140009373  jz      loc_140009285
0x140009379  cmp     [rbp+410h+var_17C], r14b
0x140009380  jnz     loc_140009285
0x140009386  lea     rbx, [rdi+50h]
0x14000938a  mov     [rsp+510h+cchWideChar], 105h; cchWideChar
0x140009392  or      r9d, 0FFFFFFFFh; cbMultiByte
0x140009396  mov     [rsp+510h+lpWideCharStr], rbx; lpWideCharStr
0x14000939b  lea     r8, [rbp+410h+Filename]; lpMultiByteStr
0x1400093a2  xor     edx, edx; dwFlags
0x1400093a4  xor     ecx, ecx; CodePage
0x1400093a6  call    cs:__imp_MultiByteToWideChar
0x1400093ac  test    eax, eax
0x1400093ae  jz      loc_140009285
0x1400093b4  lea     r8, [rdi+34h]
0x1400093b8  mov     rcx, rbx; lpWideCharStr
0x1400093bb  lea     rdx, [rdi+30h]
0x1400093bf  call    GetModuleVersion
0x1400093c4  mov     r9d, eax
0x1400093c7  mov     rcx, rdi; this
0x1400093ca  test    eax, eax
0x1400093cc  jns     short loc_1400093DF
0x1400093ce  mov     r8, [rdi]
0x1400093d1  mov     rax, [r8]
0x1400093d4  mov     r8d, 0C80h
0x1400093da  jmp     loc_14000947D
0x1400093df  lea     ebx, [r15-1]
0x1400093e3  call    ?GetTrustPolicyFromRegistry@CHost@@IEAAXXZ; CHost::GetTrustPolicyFromRegistry(void)
0x1400093e8  test    ebx, ebx
0x1400093ea  jnz     short loc_140009402
0x1400093ec  mov     rax, [rdi]
0x1400093ef  mov     rcx, rdi
0x1400093f2  mov     rax, [rax+38h]
0x1400093f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093fb  mov     esi, eax
0x1400093fd  jmp     loc_140009285
0x140009402  lea     rax, [r13+8]
0x140009406  mov     [rbp+410h+var_2AC], ebx
0x14000940c  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x140009413  mov     [rbp+410h+var_2A8], rax
0x14000941a  lea     rcx, [rsp+510h+var_4D0]; this
0x14000941f  call    ?LoadFromRegistry@CSettings@@QEAAJPEAUHKEY__@@@Z; CSettings::LoadFromRegistry(HKEY__ *)
0x140009424  mov     r9d, eax
0x140009427  test    eax, eax
0x140009429  jns     short loc_140009433
0x14000942b  mov     r8d, 0C85h
0x140009431  jmp     short loc_140009474
0x140009433  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x14000943a  lea     rcx, [rsp+510h+var_4D0]; this
0x14000943f  call    ?LoadFromRegistry@CSettings@@QEAAJPEAUHKEY__@@@Z; CSettings::LoadFromRegistry(HKEY__ *)
0x140009444  mov     r9d, eax
0x140009447  test    eax, eax
0x140009449  js      short loc_14000942B
0x14000944b  mov     al, byte ptr [rsp+510h+var_4C0+1]
0x14000944f  lea     rcx, [rsp+510h+var_4D0]; this
0x140009454  mov     [rdi+44h], al
0x140009457  call    ?Parse@CCmdLineArgs@@QEAAJXZ; CCmdLineArgs::Parse(void)
0x14000945c  mov     r9d, eax
0x14000945f  test    eax, eax
0x140009461  jns     short loc_140009490
0x140009463  cmp     eax, 8004FFFFh
0x140009468  jz      loc_140009285
0x14000946e  mov     r8d, 0C87h
0x140009474  mov     rcx, [rdi]
0x140009477  mov     rax, [rcx]
0x14000947a  mov     rcx, rdi
0x14000947d  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x140009483  add     edx, 14h
0x140009486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000948b  jmp     loc_140009285
0x140009490  mov     al, byte ptr [rsp+510h+var_4C0+1]
0x140009494  mov     cl, byte ptr [rsp+510h+var_4C0+5]
0x140009498  mov     [rdi+44h], al
0x14000949b  mov     eax, [rsp+510h+var_4D0]
0x14000949f  mov     [rdi+2Ch], eax
0x1400094a2  mov     al, byte ptr [rsp+510h+var_4CC]
0x1400094a6  mov     [rdi+45h], al
0x1400094a9  mov     al, byte ptr [rsp+510h+var_4C0+3]
0x1400094ad  mov     [rdi+47h], al
0x1400094b0  mov     al, byte ptr [rsp+510h+var_4C0+7]
0x1400094b4  mov     [rdi+49h], al
0x1400094b7  mov     [rdi+48h], cl
0x1400094ba  test    cl, cl
0x1400094bc  jz      short loc_1400094C9
0x1400094be  cmp     byte ptr [rsp+510h+var_4C0+6], r14b
0x1400094c3  jz      short loc_1400094C9
0x1400094c5  mov     [rdi+47h], sil
0x1400094c9  mov     al, [rdi+4Bh]
0x1400094cc  test    al, al
0x1400094ce  jz      short loc_1400094D4
0x1400094d0  mov     [rdi+44h], sil
0x1400094d4  cmp     byte ptr [rbp+410h+var_2A0+2], r14b
0x1400094db  jz      short loc_140009513
0x1400094dd  test    al, al
0x1400094df  jnz     loc_1400095C4
0x1400094e5  mov     [rdi+44h], r14b
0x1400094e9  cmp     [rsp+510h+var_4CA], r14b
0x1400094ee  jz      short loc_1400094FF
0x1400094f0  mov     rax, [rdi]
0x1400094f3  mov     rcx, rdi
0x1400094f6  mov     rax, [rax+10h]
0x1400094fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400094ff  mov     rax, [rdi]
0x140009502  mov     rcx, rdi
0x140009505  mov     rax, [rax+18h]
0x140009509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000950e  jmp     loc_1400095C4
0x140009513  cmp     [rsp+510h+var_4CA], r14b
0x140009518  jz      short loc_140009529
0x14000951a  mov     rax, [rdi]
0x14000951d  mov     rcx, rdi
0x140009520  mov     rax, [rax+10h]
0x140009524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009529  cmp     byte ptr [rbp+410h+var_2A0+1], r14b
0x140009530  jz      loc_1400095CC
0x140009536  mov     dword ptr [rbp+410h+Filename], r14d
0x14000953d  mov     [rbp+410h+var_27B], 100h
0x140009547  call    cs:__imp_GetACP
0x14000954d  lea     rcx, [rbp+410h+Filename]; this
0x140009554  mov     [rbp+410h+var_270], 0
0x14000955f  mov     [rbp+410h+var_274], eax
0x140009565  mov     [rbp+410h+var_268], 57h ; 'W'
0x14000956f  mov     [rbp+410h+var_264], r14w
0x140009577  mov     [rbp+410h+var_27C], r14b
0x14000957e  call    ?SaveToRegistry@CSettings@@QEAAJPEAUHKEY__@@@Z; CSettings::SaveToRegistry(HKEY__ *)
0x140009583  test    eax, eax
0x140009585  js      short loc_140009591
0x140009587  mov     ecx, 57h ; 'W'
0x14000958c  call    ChangeDefaultHost
0x140009591  mov     r10, [rdi]
0x140009594  mov     rcx, rdi
0x140009597  test    eax, eax
0x140009599  jns     short loc_1400095B3
0x14000959b  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x1400095a1  mov     r8d, 0C83h
0x1400095a7  mov     rax, [r10+8]
0x1400095ab  add     edx, 14h
0x1400095ae  jmp     loc_140009697
0x1400095b3  mov     rax, [r10+20h]
0x1400095b7  xor     edx, edx
0x1400095b9  mov     r8d, 0BEAh
0x1400095bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095c4  mov     esi, r14d
0x1400095c7  jmp     loc_140009285
0x1400095cc  mov     al, r14b
0x1400095cf  cmp     byte ptr [rbp+410h+var_2A0], r14b
0x1400095d6  jz      short loc_140009600
0x1400095d8  lea     rcx, [rsp+510h+var_4D0]; this
0x1400095dd  call    ?SaveToRegistry@CSettings@@QEAAJPEAUHKEY__@@@Z; CSettings::SaveToRegistry(HKEY__ *)
0x1400095e2  mov     r10, [rdi]
0x1400095e5  mov     rcx, rdi
0x1400095e8  test    eax, eax
0x1400095ea  js      short loc_14000959B
0x1400095ec  mov     rax, [r10+20h]
0x1400095f0  xor     edx, edx
0x1400095f2  mov     r8d, 0BEBh
0x1400095f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095fd  mov     al, sil
0x140009600  cmp     byte ptr [rbp+410h+var_2A0+3], r14b
0x140009607  jz      short loc_140009664
0x140009609  mov     ecx, [rsp+510h+var_4B8]
0x14000960d  call    ChangeDefaultHost
0x140009612  test    eax, eax
0x140009614  jns     short loc_140009627
0x140009616  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x14000961c  mov     r8d, 0C82h
0x140009622  add     edx, 14h
0x140009625  jmp     short loc_14000968D
0x140009627  cmp     [rbp+410h+var_2AC], r14d
0x14000962e  jnz     short loc_140009661
0x140009630  cmp     [rsp+510h+var_4B8], 43h ; 'C'
0x140009635  jz      short loc_14000964A
0x140009637  cmp     [rsp+510h+var_4B8], 57h ; 'W'
0x14000963c  jnz     loc_140009285
0x140009642  mov     r8d, 0BECh
0x140009648  jmp     short loc_140009650
0x14000964a  mov     r8d, 0BEDh
0x140009650  mov     rax, [rdi]
0x140009653  xor     edx, edx
0x140009655  mov     rcx, rdi
0x140009658  mov     rax, [rax+20h]
0x14000965c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009661  mov     al, sil
0x140009664  cmp     [rbp+410h+var_2AC], r14d
0x14000966b  jnz     short loc_140009676
0x14000966d  test    al, al
0x14000966f  jz      short loc_14000967E
0x140009671  jmp     loc_1400095C4
0x140009676  cmp     [rsp+510h+WideCharStr], r14w
0x14000967c  jnz     short loc_1400096AD
  ... truncated ...
```
