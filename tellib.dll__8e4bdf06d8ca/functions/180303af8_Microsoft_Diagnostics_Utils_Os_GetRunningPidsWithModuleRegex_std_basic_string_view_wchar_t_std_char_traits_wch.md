# Microsoft::Diagnostics::Utils::Os::GetRunningPidsWithModuleRegex(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::set<ulong,std::less<ulong>,std::allocator<ulong>> &,Microsoft::Diagnostics::EscalationWorkItemState *)

- ea: `0x180303af8`
- end: `0x1803041bb`
- name: `?GetRunningPidsWithModuleRegex@Os@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$set@KU?$less@K@std@@V?$allocator@K@2@@6@PEAVEscalationWorkItemState@34@@Z`
- size: `1731`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180303120`

## callees

- `0x18001d5ac`
- `0x18001e638`
- `0x1800566b0`
- `0x18007fae8`
- `0x1800fc1dc`
- `0x18012de40`
- `0x18012eb08`
- `0x1801a1c9c`
- `0x1801c7a5c`
- `0x1802f553c`
- `0x1802f55f0`
- `0x180303af8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180303b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180303da7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180303e56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180303f22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180303fdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803040af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180303b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180303da7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180303e56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180303f22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180303fdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803040af`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x180303cf6`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x180303cf6`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x180303f0e`
- `api-ms-win-core-toolhelp-l1-1-0!Process32NextW` at `0x180303f0e`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x180303b77`
- `api-ms-win-core-toolhelp-l1-1-0!Process32FirstW` at `0x180303b77`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x180303d8f`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x180303d8f`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180303b38`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180303cad`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180303b38`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180303cad`

## string_xrefs

- `0x180303c7b`: `), path(`
- `0x1803040cf`: `Failed to create process snapshot: 0x`
- `0x180303e74`: `Failed to create module snapshot: 0x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::Utils::Os::GetRunningPidsWithModuleRegex(_QWORD *a1, __int64 a2, __int64 a3)
{
  char *Toolhelp32Snapshot; // rdi
  unsigned int v6; // esi
  DWORD LastError; // ebx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  void *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  void *v14; // rax
  void *v15; // rax
  void *v16; // rax
  char *v17; // rbx
  __int64 v18; // rdi
  void *v19; // rax
  void *v20; // rax
  DWORD v21; // ebx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  void *v25; // rax
  DWORD v26; // ebx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  DWORD v30; // ebx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  void *v34; // rax
  DWORD v35; // ebx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  void *v42; // rax
  unsigned int v44; // [rsp+20h] [rbp-E0h] BYREF
  int v45; // [rsp+24h] [rbp-DCh]
  __int64 v46; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v47; // [rsp+31h] [rbp-CFh]
  __int16 v48; // [rsp+32h] [rbp-CEh]
  __int64 v49; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v50; // [rsp+48h] [rbp-B8h]
  _QWORD v51[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v52; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v53; // [rsp+61h] [rbp-9Fh]
  char v54; // [rsp+63h] [rbp-9Dh]
  int v55; // [rsp+64h] [rbp-9Ch]
  __int64 v56; // [rsp+68h] [rbp-98h]
  char v57; // [rsp+70h] [rbp-90h] BYREF
  __int16 v58; // [rsp+71h] [rbp-8Fh]
  char v59; // [rsp+73h] [rbp-8Dh]
  int v60; // [rsp+74h] [rbp-8Ch]
  __int64 v61; // [rsp+78h] [rbp-88h]
  char v62; // [rsp+80h] [rbp-80h] BYREF
  __int16 v63; // [rsp+81h] [rbp-7Fh]
  char v64; // [rsp+83h] [rbp-7Dh]
  int v65; // [rsp+84h] [rbp-7Ch]
  __int64 v66; // [rsp+88h] [rbp-78h]
  HANDLE hSnapshot; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 v68; // [rsp+99h] [rbp-67h]
  __int16 v69; // [rsp+9Ah] [rbp-66h]
  unsigned __int8 v70; // [rsp+A9h] [rbp-57h]
  __int16 v71; // [rsp+AAh] [rbp-56h]
  unsigned __int8 v72; // [rsp+B9h] [rbp-47h]
  __int16 v73; // [rsp+BAh] [rbp-46h]
  _BYTE v74[40]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v75[16]; // [rsp+F0h] [rbp-10h] BYREF
  PROCESSENTRY32W pe; // [rsp+100h] [rbp+0h] BYREF
  MODULEENTRY32W me; // [rsp+340h] [rbp+240h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7C8h] [rbp+6C8h]

  v49 = a2;
  Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(2u, 0);
  hSnapshot = Toolhelp32Snapshot;
  if ( (unsigned __int64)(Toolhelp32Snapshot - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    memset_0(&pe.cntUsage, 0, 0x234u);
    pe.dwSize = 568;
    v6 = 0;
    if ( !Process32FirstW(Toolhelp32Snapshot, &pe) )
    {
      LastError = GetLastError();
      if ( a3 )
      {
        v8 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        LOBYTE(v49) = 1;
        *(_WORD *)((char *)&v49 + 1) = BYTE1(v44);
        BYTE3(v49) = 0;
        HIDWORD(v49) = 2097153;
        v50 = 0;
        v9 = Microsoft::Diagnostics::WideStringStream::operator<<(v8, &v49);
        v10 = Microsoft::Diagnostics::WideStringStream::operator<<(v9, LastError);
        HIWORD(v44) = 0;
        LOBYTE(v49) = 1;
        *(_WORD *)((char *)&v49 + 1) = BYTE1(v44);
        BYTE3(v49) = 0;
        HIDWORD(v49) = 0x200000;
        v50 = 0;
        v11 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v10, &v49);
        Microsoft::Diagnostics::WideStringStream::operator<<(v11);
      }
      if ( !LastError )
        goto LABEL_37;
      v12 = 1618;
LABEL_36:
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v12,
             (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
             (const char *)LastError,
             v44);
      goto LABEL_37;
    }
    while ( 1 )
    {
      if ( a3 )
      {
        v13 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
        v14 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v13, pe.th32ProcessID);
        v15 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v14);
        v16 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v15);
        Microsoft::Diagnostics::WideStringStream::operator<<(v16);
      }
      v17 = (char *)CreateToolhelp32Snapshot(8u, pe.th32ProcessID);
      v51[0] = v17;
      if ( (unsigned __int64)(v17 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        v26 = GetLastError();
        if ( a3 )
        {
          v27 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
          v73 = 0;
          v62 = 1;
          v63 = v72;
          v64 = 0;
          v65 = 2097153;
          v66 = 0;
          v28 = Microsoft::Diagnostics::WideStringStream::operator<<(v27, &v62);
          v29 = Microsoft::Diagnostics::WideStringStream::operator<<(v28, v26);
          v48 = 0;
          LOBYTE(v44) = 1;
          *(_WORD *)((char *)&v44 + 1) = v47;
          HIBYTE(v44) = 0;
          v45 = 0x200000;
          v46 = 0;
          v25 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v29, &v44);
          goto LABEL_22;
        }
      }
      else
      {
        memset_0(&me.th32ModuleID, 0, 0x434u);
        me.dwSize = 1080;
        if ( !Module32FirstW(v17, &me) )
        {
          v35 = GetLastError();
          if ( a3 )
          {
            v36 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
            v48 = 0;
            LOBYTE(v44) = 1;
            *(_WORD *)((char *)&v44 + 1) = v47;
            HIBYTE(v44) = 0;
            v45 = 2097153;
            v46 = 0;
            v37 = Microsoft::Diagnostics::WideStringStream::operator<<(v36, &v44);
            v38 = Microsoft::Diagnostics::WideStringStream::operator<<(v37, v35);
            v48 = 0;
            LOBYTE(v44) = 1;
            *(_WORD *)((char *)&v44 + 1) = v47;
            HIBYTE(v44) = 0;
            v45 = 0x200000;
            v46 = 0;
            Microsoft::Diagnostics::WideStringStream::operator<<(v38, &v44);
          }
          if ( v35 )
            v6 = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0x671,
                   (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                   (const char *)v35,
                   v44);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(v51);
          goto LABEL_37;
        }
        v18 = v49;
        do
        {
          std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(
            v74,
            *a1,
            a1[1]);
          if ( (unsigned __int8)std::regex_search<wchar_t,std::regex_traits<wchar_t>>(me.szModule, v74) )
          {
            if ( a3 )
            {
              v19 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
              v20 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v19);
              Microsoft::Diagnostics::WideStringStream::operator<<(v20);
            }
            std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::emplace<unsigned long &>(
              v18,
              v75,
              &pe.th32ProcessID);
          }
          std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(v74);
        }
        while ( Module32NextW(v17, &me) );
        Toolhelp32Snapshot = (char *)hSnapshot;
        v21 = GetLastError();
        if ( v21 != 18 && a3 )
        {
          v22 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
          v69 = 0;
          v52 = 1;
          v53 = v68;
          v54 = 0;
          v55 = 2097153;
          v56 = 0;
          v23 = Microsoft::Diagnostics::WideStringStream::operator<<(v22, &v52);
          v24 = Microsoft::Diagnostics::WideStringStream::operator<<(v23, v21);
          v71 = 0;
          v57 = 1;
          v58 = v70;
          v59 = 0;
          v60 = 0x200000;
          v61 = 0;
          v25 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v24, &v57);
LABEL_22:
          Microsoft::Diagnostics::WideStringStream::operator<<(v25);
        }
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(v51);
      if ( !Process32NextW(Toolhelp32Snapshot, &pe) )
      {
        v30 = GetLastError();
        if ( v30 != 18 && a3 )
        {
          v31 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
          v48 = 0;
          LOBYTE(v44) = 1;
          *(_WORD *)((char *)&v44 + 1) = v47;
          HIBYTE(v44) = 0;
          v45 = 2097153;
          v46 = 0;
          v32 = Microsoft::Diagnostics::WideStringStream::operator<<(v31, &v44);
          v33 = Microsoft::Diagnostics::WideStringStream::operator<<(v32, v30);
          v48 = 0;
          LOBYTE(v44) = 1;
          *(_WORD *)((char *)&v44 + 1) = v47;
          HIBYTE(v44) = 0;
          v45 = 0x200000;
          v46 = 0;
          v34 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v33, &v44);
          Microsoft::Diagnostics::WideStringStream::operator<<(v34);
        }
        goto LABEL_37;
      }
    }
  }
  LastError = GetLastError();
  v6 = 0;
  if ( a3 )
  {
    v39 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
    v48 = 0;
    LOBYTE(v44) = 1;
    *(_WORD *)((char *)&v44 + 1) = v47;
    HIBYTE(v44) = 0;
    v45 = 2097153;
    v46 = 0;
    v40 = Microsoft::Diagnostics::WideStringStream::operator<<(v39, &v44);
    v41 = Microsoft::Diagnostics::WideStringStream::operator<<(v40, LastError);
    v48 = 0;
    LOBYTE(v44) = 1;
    *(_WORD *)((char *)&v44 + 1) = v47;
    HIBYTE(v44) = 0;
    v45 = 0x200000;
    v46 = 0;
    v42 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v41, &v44);
    Microsoft::Diagnostics::WideStringStream::operator<<(v42);
  }
  if ( LastError )
  {
    v12 = 1606;
    goto LABEL_36;
  }
LABEL_37:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&int CloseHandle(void *)>>(&hSnapshot);
  return v6;
}

```

## disassembly

```asm
0x180303af8  mov     [rsp-8+arg_18], rbx
0x180303afd  push    rbp
0x180303afe  push    rsi
0x180303aff  push    rdi
0x180303b00  push    r12
0x180303b02  push    r13
0x180303b04  push    r14
0x180303b06  push    r15
0x180303b08  lea     rbp, [rsp-690h]
0x180303b10  sub     rsp, 790h
0x180303b17  mov     rax, cs:__security_cookie
0x180303b1e  xor     rax, rsp
0x180303b21  mov     [rbp+6C0h+var_40], rax
0x180303b28  mov     r14, r8
0x180303b2b  mov     [rsp+7C0h+var_780], rdx
0x180303b30  mov     r13, rcx
0x180303b33  xor     edx, edx; th32ProcessID
0x180303b35  lea     ecx, [rdx+2]; dwFlags
0x180303b38  call    cs:__imp_CreateToolhelp32Snapshot
0x180303b3f  nop     dword ptr [rax+rax+00h]
0x180303b44  mov     rdi, rax
0x180303b47  mov     [rbp+6C0h+hSnapshot], rax
0x180303b4b  dec     rax
0x180303b4e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180303b52  ja      loc_1803040AF
0x180303b58  xor     edx, edx; Val
0x180303b5a  mov     r8d, 234h; Size
0x180303b60  lea     rcx, [rbp+6C0h+pe.cntUsage]; void *
0x180303b64  call    memset_0
0x180303b69  mov     [rbp+6C0h+pe.dwSize], 238h
0x180303b70  lea     rdx, [rbp+6C0h+pe]; lppe
0x180303b74  mov     rcx, rdi; hSnapshot
0x180303b77  call    cs:__imp_Process32FirstW
0x180303b7e  nop     dword ptr [rax+rax+00h]
0x180303b83  xor     esi, esi
0x180303b85  test    eax, eax
0x180303b87  jnz     loc_180303C52
0x180303b8d  call    cs:__imp_GetLastError
0x180303b94  nop     dword ptr [rax+rax+00h]
0x180303b99  mov     ebx, eax
0x180303b9b  test    r14, r14
0x180303b9e  jz      loc_180303C40
0x180303ba4  lea     rcx, [r14+0A8h]; Src
0x180303bab  lea     rdx, aFailedToEnumer_0; "Failed to enumerate processes (1): 0x"
0x180303bb2  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180303bb7  mov     word ptr [rsp+7C0h+var_7A0+2], si
0x180303bbc  lea     r15d, [rsi+1]
0x180303bc0  mov     byte ptr [rsp+7C0h+var_780], r15b
0x180303bc5  movzx   ecx, word ptr [rsp+21h]
0x180303bca  mov     word ptr [rsp+7C0h+var_780+1], cx
0x180303bcf  mov     cl, byte ptr [rsp+7C0h+var_7A0+3]
0x180303bd3  mov     byte ptr [rsp+7C0h+var_780+3], cl
0x180303bd7  mov     dword ptr [rsp+7C0h+var_780+4], 200001h
0x180303bdf  mov     [rsp+7C0h+var_778], rsi
0x180303be4  lea     rdx, [rsp+7C0h+var_780]
0x180303be9  mov     rcx, rax
0x180303bec  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x180303bf1  mov     edx, ebx
0x180303bf3  mov     rcx, rax
0x180303bf6  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x180303bfb  mov     word ptr [rsp+7C0h+var_7A0+2], si
0x180303c00  mov     byte ptr [rsp+7C0h+var_780], r15b
0x180303c05  movzx   ecx, word ptr [rsp+21h]
0x180303c0a  mov     word ptr [rsp+7C0h+var_780+1], cx
0x180303c0f  mov     cl, byte ptr [rsp+7C0h+var_7A0+3]
0x180303c13  mov     byte ptr [rsp+7C0h+var_780+3], cl
0x180303c17  mov     dword ptr [rsp+7C0h+var_780+4], 200000h
0x180303c1f  mov     [rsp+7C0h+var_778], rsi
0x180303c24  lea     rdx, [rsp+7C0h+var_780]
0x180303c29  mov     rcx, rax
0x180303c2c  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x180303c31  lea     rdx, asc_1803721B4; "\r\n"
0x180303c38  mov     rcx, rax; Src
0x180303c3b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180303c40  test    ebx, ebx
0x180303c42  jz      loc_180304185
0x180303c48  mov     edx, 652h
0x180303c4d  jmp     loc_18030416D
0x180303c52  mov     r15d, 1
0x180303c58  test    r14, r14
0x180303c5b  jz      short loc_180303CA5
0x180303c5d  lea     rcx, [r14+0A8h]; Src
0x180303c64  lea     rdx, aEnumeratingMod; "Enumerating modules for pid("
0x180303c6b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180303c70  mov     edx, [rbp+6C0h+pe.th32ProcessID]
0x180303c73  mov     rcx, rax
0x180303c76  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x180303c7b  lea     rdx, aPath_1; "), path("
0x180303c82  mov     rcx, rax; Src
0x180303c85  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180303c8a  lea     rdx, [rbp+6C0h+pe.szExeFile]
0x180303c8e  mov     rcx, rax; Src
0x180303c91  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180303c96  lea     rdx, asc_1803B6360; ")\r\n"
0x180303c9d  mov     rcx, rax; Src
0x180303ca0  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180303ca5  mov     edx, [rbp+6C0h+pe.th32ProcessID]; th32ProcessID
0x180303ca8  mov     ecx, 8; dwFlags
0x180303cad  call    cs:__imp_CreateToolhelp32Snapshot
0x180303cb4  nop     dword ptr [rax+rax+00h]
0x180303cb9  mov     rbx, rax
0x180303cbc  mov     [rsp+7C0h+var_770], rax
0x180303cc1  dec     rax
0x180303cc4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180303cc8  ja      loc_180303E56
0x180303cce  xor     edx, edx; Val
0x180303cd0  mov     r8d, 434h; Size
0x180303cd6  lea     rcx, [rbp+6C0h+me.th32ModuleID]; void *
0x180303cdd  call    memset_0
0x180303ce2  mov     [rbp+6C0h+me.dwSize], 438h
0x180303cec  lea     rdx, [rbp+6C0h+me]; lpme
0x180303cf3  mov     rcx, rbx; hSnapshot
0x180303cf6  call    cs:__imp_Module32FirstW
0x180303cfd  nop     dword ptr [rax+rax+00h]
0x180303d02  test    eax, eax
0x180303d04  jz      loc_180303FDF
0x180303d0a  mov     rdi, [rsp+7C0h+var_780]
0x180303d0f  mov     r8, [r13+8]
0x180303d13  mov     rdx, [r13+0]
0x180303d17  lea     rcx, [rbp+6C0h+var_6F8]
0x180303d1b  call    ??0?$basic_regex@_WV?$regex_traits@_W@std@@@std@@QEAA@PEB_W_KW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(wchar_t const *,unsigned __int64,std::regex_constants::syntax_option_type)
0x180303d20  nop
0x180303d21  lea     rdx, [rbp+6C0h+var_6F8]
0x180303d25  lea     rcx, [rbp+6C0h+me.szModule]
0x180303d2c  call    ??$regex_search@_WV?$regex_traits@_W@std@@@std@@YA_NPEB_WAEBV?$basic_regex@_WV?$regex_traits@_W@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_search<wchar_t,std::regex_traits<wchar_t>>(wchar_t const *,std::basic_regex<wchar_t,std::regex_traits<wchar_t>> const &,std::regex_constants::match_flag_type)
0x180303d31  test    al, al
0x180303d33  jz      short loc_180303D7C
0x180303d35  test    r14, r14
0x180303d38  jz      short loc_180303D6B
0x180303d3a  lea     rcx, [r14+0A8h]; Src
0x180303d41  lea     rdx, aFoundMatchingM; "Found matching module "
0x180303d48  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180303d4d  lea     rdx, [rbp+6C0h+me.szModule]
0x180303d54  mov     rcx, rax; Src
0x180303d57  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180303d5c  lea     rdx, asc_1803721B4; "\r\n"
0x180303d63  mov     rcx, rax; Src
0x180303d66  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180303d6b  lea     r8, [rbp+6C0h+pe.th32ProcessID]
0x180303d6f  lea     rdx, [rbp+6C0h+var_6D0]
0x180303d73  mov     rcx, rdi
0x180303d76  call    ??$emplace@AEAK@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@std@@_N@1@AEAK@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::emplace<ulong &>(ulong &)
0x180303d7b  nop
0x180303d7c  lea     rcx, [rbp+6C0h+var_6F8]
0x180303d80  call    ??1?$basic_regex@_WV?$regex_traits@_W@std@@@std@@QEAA@XZ; std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(void)
0x180303d85  lea     rdx, [rbp+6C0h+me]; lpme
0x180303d8c  mov     rcx, rbx; hSnapshot
0x180303d8f  call    cs:__imp_Module32NextW
0x180303d96  nop     dword ptr [rax+rax+00h]
0x180303d9b  test    eax, eax
0x180303d9d  jnz     loc_180303D0F
0x180303da3  mov     rdi, [rbp+6C0h+hSnapshot]
0x180303da7  call    cs:__imp_GetLastError
0x180303dae  nop     dword ptr [rax+rax+00h]
0x180303db3  mov     ebx, eax
0x180303db5  cmp     eax, 12h
0x180303db8  jz      loc_180303EFD
0x180303dbe  test    r14, r14
0x180303dc1  jz      loc_180303EFD
0x180303dc7  lea     rcx, [r14+0A8h]; Src
0x180303dce  lea     rdx, aFailedToEnumer_2; "Failed to enumerate modules (2): 0x"
0x180303dd5  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180303dda  mov     [rbp+6C0h+var_726], si
0x180303dde  mov     [rsp+7C0h+var_760], r15b
0x180303de3  movzx   ecx, word ptr [rbp-67h]
0x180303de7  mov     [rsp+7C0h+var_75F], cx
0x180303dec  mov     cl, byte ptr [rbp+6C0h+var_726+1]
0x180303def  mov     [rsp+7C0h+var_75D], cl
0x180303df3  mov     [rsp+7C0h+var_75C], 200001h
0x180303dfb  mov     [rsp+7C0h+var_758], rsi
0x180303e00  lea     rdx, [rsp+7C0h+var_760]
0x180303e05  mov     rcx, rax
0x180303e08  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x180303e0d  mov     edx, ebx
0x180303e0f  mov     rcx, rax
0x180303e12  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x180303e17  mov     [rbp+6C0h+var_716], si
0x180303e1b  mov     [rsp+7C0h+var_750], r15b
0x180303e20  movzx   ecx, word ptr [rbp-57h]
0x180303e24  mov     [rsp+7C0h+var_74F], cx
0x180303e29  mov     cl, byte ptr [rbp+6C0h+var_716+1]
0x180303e2c  mov     [rsp+7C0h+var_74D], cl
0x180303e30  mov     [rsp+7C0h+var_74C], 200000h
0x180303e38  mov     [rsp+7C0h+var_748], rsi
0x180303e3d  lea     rdx, [rsp+7C0h+var_750]
0x180303e42  mov     rcx, rax
0x180303e45  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x180303e4a  lea     rdx, aNonFatal_1; ". Non-fatal...\r\n"
0x180303e51  jmp     loc_180303EF4
0x180303e56  call    cs:__imp_GetLastError
0x180303e5d  nop     dword ptr [rax+rax+00h]
0x180303e62  mov     ebx, eax
0x180303e64  test    r14, r14
0x180303e67  jz      loc_180303EFD
0x180303e6d  lea     rcx, [r14+0A8h]; Src
0x180303e74  lea     rdx, aFailedToCreate; "Failed to create module snapshot: 0x"
0x180303e7b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180303e80  mov     [rbp+6C0h+var_706], si
0x180303e84  mov     [rbp+6C0h+var_740], r15b
0x180303e88  movzx   ecx, word ptr [rbp-47h]
0x180303e8c  mov     [rbp+6C0h+var_73F], cx
0x180303e90  mov     cl, byte ptr [rbp+6C0h+var_706+1]
0x180303e93  mov     [rbp+6C0h+var_73D], cl
0x180303e96  mov     [rbp+6C0h+var_73C], 200001h
0x180303e9d  mov     [rbp+6C0h+var_738], rsi
0x180303ea1  lea     rdx, [rbp+6C0h+var_740]
0x180303ea5  mov     rcx, rax
0x180303ea8  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x180303ead  mov     edx, ebx
0x180303eaf  mov     rcx, rax
0x180303eb2  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x180303eb7  mov     [rsp+7C0h+var_78E], si
0x180303ebc  mov     byte ptr [rsp+7C0h+var_7A0], r15b
0x180303ec1  movzx   ecx, word ptr [rsp+31h]
0x180303ec6  mov     [rsp+21h], cx
0x180303ecb  mov     cl, byte ptr [rsp+7C0h+var_78E+1]
0x180303ecf  mov     byte ptr [rsp+7C0h+var_7A0+3], cl
0x180303ed3  mov     [rsp+7C0h+var_79C], 200000h
0x180303edb  mov     [rsp+7C0h+var_798], rsi
0x180303ee0  lea     rdx, [rsp+7C0h+var_7A0]
0x180303ee5  mov     rcx, rax
0x180303ee8  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x180303eed  lea     rdx, aSkipping; ". Skipping...\r\n"
0x180303ef4  mov     rcx, rax; Src
0x180303ef7  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180303efc  nop
0x180303efd  lea     rcx, [rsp+7C0h+var_770]
0x180303f02  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@$$A6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (void *),&CloseHandle(void *)>>(void)
0x180303f07  lea     rdx, [rbp+6C0h+pe]; lppe
0x180303f0b  mov     rcx, rdi; hSnapshot
0x180303f0e  call    cs:__imp_Process32NextW
0x180303f15  nop     dword ptr [rax+rax+00h]
0x180303f1a  test    eax, eax
0x180303f1c  jnz     loc_180303C58
0x180303f22  call    cs:__imp_GetLastError
0x180303f29  nop     dword ptr [rax+rax+00h]
0x180303f2e  mov     ebx, eax
0x180303f30  cmp     eax, 12h
0x180303f33  jz      loc_180304185
0x180303f39  test    r14, r14
0x180303f3c  jz      loc_180304185
0x180303f42  lea     rcx, [r14+0A8h]; Src
0x180303f49  lea     rdx, aFailedToEnumer_1; "Failed to enumerate processes (2): 0x"
0x180303f50  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180303f55  mov     [rsp+7C0h+var_78E], si
0x180303f5a  mov     byte ptr [rsp+7C0h+var_7A0], r15b
0x180303f5f  movzx   ecx, word ptr [rsp+31h]
0x180303f64  mov     [rsp+21h], cx
0x180303f69  mov     cl, byte ptr [rsp+7C0h+var_78E+1]
0x180303f6d  mov     byte ptr [rsp+7C0h+var_7A0+3], cl
0x180303f71  mov     [rsp+7C0h+var_79C], 200001h
0x180303f79  mov     [rsp+7C0h+var_798], rsi
0x180303f7e  lea     rdx, [rsp+7C0h+var_7A0]
0x180303f83  mov     rcx, rax
0x180303f86  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x180303f8b  mov     edx, ebx
0x180303f8d  mov     rcx, rax
0x180303f90  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x180303f95  mov     [rsp+7C0h+var_78E], si
0x180303f9a  mov     byte ptr [rsp+7C0h+var_7A0], r15b
0x180303f9f  movzx   ecx, word ptr [rsp+31h]
0x180303fa4  mov     [rsp+21h], cx
0x180303fa9  mov     cl, byte ptr [rsp+7C0h+var_78E+1]
0x180303fad  mov     byte ptr [rsp+7C0h+var_7A0+3], cl
0x180303fb1  mov     [rsp+7C0h+var_79C], 200000h
0x180303fb9  mov     [rsp+7C0h+var_798], rsi
0x180303fbe  lea     rdx, [rsp+7C0h+var_7A0]
0x180303fc3  mov     rcx, rax
0x180303fc6  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x180303fcb  lea     rdx, aNonFatal_1; ". Non-fatal...\r\n"
0x180303fd2  mov     rcx, rax; Src
0x180303fd5  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180303fda  jmp     loc_180304185
0x180303fdf  call    cs:__imp_GetLastError
0x180303fe6  nop     dword ptr [rax+rax+00h]
0x180303feb  mov     ebx, eax
0x180303fed  test    r14, r14
0x180303ff0  jz      loc_18030407F
0x180303ff6  lea     rcx, [r14+0A8h]; Src
0x180303ffd  lea     rdx, aFailedToEnumer; "Failed to enumerate modules (1): 0x"
0x180304004  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180304009  mov     [rsp+7C0h+var_78E], si
0x18030400e  mov     byte ptr [rsp+7C0h+var_7A0], r15b
0x180304013  movzx   ecx, word ptr [rsp+31h]
0x180304018  mov     [rsp+21h], cx
0x18030401d  mov     cl, byte ptr [rsp+7C0h+var_78E+1]
0x180304021  mov     byte ptr [rsp+7C0h+var_7A0+3], cl
0x180304025  mov     [rsp+7C0h+var_79C], 200001h
0x18030402d  mov     [rsp+7C0h+var_798], rsi
0x180304032  lea     rdx, [rsp+7C0h+var_7A0]
0x180304037  mov     rcx, rax
0x18030403a  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18030403f  mov     edx, ebx
0x180304041  mov     rcx, rax
0x180304044  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x180304049  mov     [rsp+7C0h+var_78E], si
0x18030404e  mov     byte ptr [rsp+7C0h+var_7A0], r15b; unsigned int
0x180304053  movzx   ecx, word ptr [rsp+31h]
0x180304058  mov     [rsp+21h], cx
0x18030405d  mov     cl, byte ptr [rsp+7C0h+var_78E+1]
  ... truncated ...
```
