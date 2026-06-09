# Windows::Registry::GetValue(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x180083744`
- end: `0x180083c0c`
- name: `?GetValue@Registry@Windows@@QEAA?AU?$pair@JV?$optional@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@QEAUHKEY__@@V?$basic_zstring_view@_W@wil@@11@Z`
- size: `1224`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int128 *, _OWORD *, const WCHAR **)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18006e110`
- `0x18006e240`
- `0x180084770`

## callees

- `0x180011320`
- `0x180011680`
- `0x180039d4c`
- `0x18005eb90`
- `0x180083744`
- `0x180083c20`
- `0x180084cd4`
- `0x1800855a0`
- `0x1800dd930`
- `0x1800dff58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800837e6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180083883`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008392f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180083a1c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800837e6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180083883`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008392f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180083a1c`

## string_xrefs

- `0x18008382d`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x180083ad5`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x180083beb`: `Registry type unsupported`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Registry::GetValue(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int128 *a4,
        _OWORD *a5,
        const WCHAR **a6)
{
  const WCHAR *v7; // rsi
  const WCHAR *v8; // rdx
  LSTATUS ValueW; // eax
  int v10; // edx
  LPCWSTR *v11; // rax
  const WCHAR *v12; // rdx
  unsigned int v13; // ebx
  const WCHAR *v14; // rdx
  DWORD *v15; // rax
  const WCHAR *v16; // rdx
  DWORD *v17; // rax
  unsigned __int64 v18; // rdx
  DWORD *v19; // rax
  LPCWSTR *v20; // rax
  _QWORD *v21; // rbx
  bool v22; // zf
  unsigned int v23; // eax
  DWORD pdwType; // [rsp+44h] [rbp-75h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-71h] BYREF
  DWORD pExceptionObject[4]; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int64 v28; // [rsp+60h] [rbp-59h]
  unsigned __int64 v29; // [rsp+68h] [rbp-51h]
  __int128 pvData; // [rsp+70h] [rbp-49h] BYREF
  _QWORD v31[4]; // [rsp+80h] [rbp-39h] BYREF
  char v32; // [rsp+A0h] [rbp-19h]
  char v33; // [rsp+A8h] [rbp-11h]
  LPCWSTR lpSubKey[3]; // [rsp+B0h] [rbp-9h] BYREF
  unsigned __int64 v35; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+4Fh]

  *(_QWORD *)pExceptionObject = a2;
  v33 = 0;
  *(_OWORD *)pExceptionObject = *a5;
  pvData = *a4;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, &pvData, pExceptionObject);
  pdwType = 0;
  pcbData = 0;
  v7 = *a6;
  v8 = (const WCHAR *)lpSubKey;
  if ( v35 > 7 )
    v8 = lpSubKey[0];
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v8, v7, 0xFFFFu, &pdwType, 0, &pcbData);
  v10 = ValueW;
  if ( ValueW != 2 && ValueW != 1018 )
  {
    v11 = lpSubKey;
    if ( v35 > 7 )
      v11 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x46,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
      (const char *)(unsigned int)v10,
      (unsigned int)"%ws[%ws]",
      (const char *)v11,
      v7);
    switch ( pdwType )
    {
      case 4u:
        LODWORD(pvData) = 0;
        pExceptionObject[0] = 4;
        v12 = (const WCHAR *)lpSubKey;
        if ( v35 > 7 )
          v12 = lpSubKey[0];
        v13 = RegGetValueW(HKEY_LOCAL_MACHINE, v12, v7, 0x10u, &pdwType, &pvData, pExceptionObject);
        if ( !v13 )
        {
          if ( v33 )
          {
            if ( v32 )
            {
              if ( v32 != -1 && (unsigned __int64)v32 >= 2 )
                std::wstring::~wstring(v31);
              LODWORD(v31[0]) = pvData;
              v32 = 0;
            }
            else
            {
              LODWORD(v31[0]) = pvData;
            }
            goto LABEL_56;
          }
          LODWORD(v31[0]) = pvData;
          v32 = 0;
          goto LABEL_31;
        }
        break;
      case 0xBu:
        *(_QWORD *)&pvData = 0;
        pExceptionObject[0] = 8;
        v14 = (const WCHAR *)lpSubKey;
        if ( v35 > 7 )
          v14 = lpSubKey[0];
        v13 = RegGetValueW(HKEY_LOCAL_MACHINE, v14, v7, 0x40u, &pdwType, &pvData, pExceptionObject);
        if ( !v13 )
        {
          if ( v33 )
          {
            if ( v32 == 1 )
            {
              v31[0] = pvData;
            }
            else
            {
              if ( v32 != -1 && (unsigned __int64)v32 >= 2 )
                std::wstring::~wstring(v31);
              v31[0] = pvData;
              v32 = 1;
            }
            goto LABEL_56;
          }
          v31[0] = pvData;
          v32 = 1;
LABEL_31:
          v33 = 1;
          goto LABEL_56;
        }
        break;
      case 1u:
        *(_OWORD *)pExceptionObject = 0;
        v28 = 0;
        v29 = 7;
        LOWORD(pExceptionObject[0]) = 0;
        if ( (unsigned __int64)pcbData >> 1 )
        {
          std::wstring::append(pExceptionObject);
        }
        else
        {
          v28 = 0;
          LOWORD(pExceptionObject[0]) = 0;
        }
        v15 = pExceptionObject;
        if ( v29 > 7 )
          v15 = *(DWORD **)pExceptionObject;
        v16 = (const WCHAR *)lpSubKey;
        if ( v35 > 7 )
          v16 = lpSubKey[0];
        v13 = RegGetValueW(HKEY_LOCAL_MACHINE, v16, v7, 2u, &pdwType, v15, &pcbData);
        if ( !v13 )
        {
          while ( v28 )
          {
            v17 = pExceptionObject;
            if ( v29 > 7 )
              v17 = *(DWORD **)pExceptionObject;
            v18 = v28 - 1;
            if ( *((_WORD *)v17 + v28 - 1) )
              break;
            if ( v18 > v28 )
            {
              std::wstring::append(pExceptionObject);
            }
            else
            {
              --v28;
              v19 = pExceptionObject;
              if ( v29 > 7 )
                v19 = *(DWORD **)pExceptionObject;
              *((_WORD *)v19 + v18) = 0;
            }
          }
          std::optional<std::variant<unsigned int,unsigned __int64,std::wstring>>::operator=<std::wstring &,0>(v31);
        }
        std::wstring::~wstring(pExceptionObject);
        break;
      default:
        std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Registry type unsupported");
        throw (std::logic_error *)pExceptionObject;
    }
    if ( v13 == 2 || v13 == 1018 || v13 == 1168 )
    {
      *(_DWORD *)a2 = (unsigned __int16)v13 | 0x80070000;
      *(_BYTE *)(a2 + 48) = 0;
LABEL_66:
      std::wstring::~wstring(lpSubKey);
      if ( !v33 || v32 == -1 || !v32 )
        return a2;
      v22 = v32 == 1;
      goto LABEL_77;
    }
LABEL_56:
    v20 = lpSubKey;
    if ( v35 > 7 )
      v20 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x8B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
      (const char *)v13,
      (unsigned int)"%ws[%ws]",
      (const char *)v20,
      v7);
    *(_DWORD *)a2 = 0;
    v21 = (_QWORD *)(a2 + 8);
    *(_QWORD *)pExceptionObject = a2 + 8;
    *(_BYTE *)(a2 + 48) = 0;
    if ( v33 )
    {
      *(_QWORD *)&pvData = a2 + 8;
      *(_BYTE *)(a2 + 40) = -1;
      if ( v32 != -1 )
      {
        if ( v32 )
        {
          if ( v32 == 1 )
          {
            *v21 = v31[0];
            *(_BYTE *)(a2 + 40) = 1;
          }
          else
          {
            std::wstring::wstring(a2 + 8, v31);
            *(_BYTE *)(a2 + 40) = 2;
          }
        }
        else
        {
          *(_DWORD *)v21 = v31[0];
          *(_BYTE *)(a2 + 40) = 0;
        }
      }
      *(_BYTE *)(a2 + 48) = 1;
    }
    goto LABEL_66;
  }
  v23 = (unsigned __int16)ValueW | 0x80070000;
  if ( v10 <= 0 )
    v23 = v10;
  *(_DWORD *)a2 = v23;
  *(_BYTE *)(a2 + 48) = 0;
  std::wstring::~wstring(lpSubKey);
  if ( v33 && v32 != -1 && v32 )
  {
    v22 = v32 == 1;
LABEL_77:
    if ( !v22 )
      std::wstring::~wstring(v31);
  }
  return a2;
}

```

## disassembly

```asm
0x180083744  mov     [rsp-8+arg_0], rbx
0x180083749  push    rbp
0x18008374a  push    rsi
0x18008374b  push    rdi
0x18008374c  push    r13
0x18008374e  push    r14
0x180083750  lea     rbp, [rsp-27h]
0x180083755  sub     rsp, 0E0h
0x18008375c  mov     rax, cs:__security_cookie
0x180083763  xor     rax, rsp
0x180083766  mov     [rbp+47h+var_30], rax
0x18008376a  mov     rdi, rdx
0x18008376d  mov     qword ptr [rbp+47h+pExceptionObject], rdx
0x180083771  mov     rax, [rbp+47h+arg_20]
0x180083775  mov     rbx, [rbp+47h+arg_28]
0x180083779  xor     r14d, r14d
0x18008377c  mov     [rbp+47h+var_58], r14b
0x180083780  movaps  xmm0, xmmword ptr [rax]
0x180083783  movdqa  xmmword ptr [rbp+47h+pExceptionObject], xmm0
0x180083788  movaps  xmm1, xmmword ptr [r9]
0x18008378c  movdqa  [rbp+47h+var_90], xmm1
0x180083791  lea     r9, [rbp+47h+pExceptionObject]
0x180083795  lea     r8, [rbp+47h+var_90]
0x180083799  lea     rdx, [rbp+47h+lpSubKey]
0x18008379d  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x1800837a2  nop
0x1800837a3  mov     [rbp+47h+var_BC], r14d
0x1800837a7  mov     [rbp+47h+var_B8], r14d
0x1800837ab  mov     rsi, [rbx]
0x1800837ae  lea     rdx, [rbp+47h+lpSubKey]
0x1800837b2  cmp     [rbp+47h+var_38], 7
0x1800837b7  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x1800837bc  lea     rax, [rbp+47h+var_B8]
0x1800837c0  mov     [rsp+100h+pcbData], rax; pcbData
0x1800837c5  mov     [rsp+100h+pvData], r14; pvData
0x1800837ca  lea     rax, [rbp+47h+var_BC]
0x1800837ce  mov     [rsp+100h+pdwType], rax; pdwType
0x1800837d3  mov     r9d, 0FFFFh; dwFlags
0x1800837d9  mov     r8, rsi; lpValue
0x1800837dc  mov     rbx, 0FFFFFFFF80000002h
0x1800837e3  mov     rcx, rbx; hkey
0x1800837e6  call    cs:__imp_RegGetValueW
0x1800837ec  mov     edx, eax
0x1800837ee  cmp     eax, 2
0x1800837f1  jz      loc_180083B82
0x1800837f7  cmp     eax, 3FAh
0x1800837fc  jz      loc_180083B82
0x180083802  lea     rax, [rbp+47h+lpSubKey]
0x180083806  cmp     [rbp+47h+var_38], 7
0x18008380b  cmova   rax, [rbp+47h+lpSubKey]
0x180083810  mov     rcx, [rbp+4Fh]; this
0x180083814  mov     [rsp+100h+pcbData], rsi
0x180083819  mov     [rsp+100h+pvData], rax; char *
0x18008381e  lea     r13, aWsWs; "%ws[%ws]"
0x180083825  mov     [rsp+100h+pdwType], r13; unsigned int
0x18008382a  mov     r9d, edx; char *
0x18008382d  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180083834  lea     edx, [r14+46h]; void *
0x180083838  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18008383d  mov     eax, [rbp+47h+var_BC]
0x180083840  cmp     eax, 4
0x180083843  jnz     loc_1800838E6
0x180083849  mov     dword ptr [rbp+47h+var_90], r14d
0x18008384d  mov     [rbp+47h+pExceptionObject], eax
0x180083850  lea     rdx, [rbp+47h+lpSubKey]
0x180083854  cmp     [rbp+47h+var_38], 7
0x180083859  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18008385e  lea     rax, [rbp+47h+pExceptionObject]
0x180083862  mov     [rsp+100h+pcbData], rax; pcbData
0x180083867  lea     rax, [rbp+47h+var_90]
0x18008386b  mov     [rsp+100h+pvData], rax; pvData
0x180083870  lea     rax, [rbp+47h+var_BC]
0x180083874  mov     [rsp+100h+pdwType], rax; pdwType
0x180083879  lea     r9d, [r14+10h]; dwFlags
0x18008387d  mov     r8, rsi; lpValue
0x180083880  mov     rcx, rbx; hkey
0x180083883  call    cs:__imp_RegGetValueW
0x180083889  mov     ebx, eax
0x18008388b  test    eax, eax
0x18008388d  jnz     loc_180083A90
0x180083893  cmp     [rbp+47h+var_58], r14b
0x180083897  jz      short loc_1800838D7
0x180083899  movsx   rax, [rbp+47h+var_60]
0x18008389e  test    al, al
0x1800838a0  jnz     short loc_1800838AD
0x1800838a2  mov     eax, dword ptr [rbp+47h+var_90]
0x1800838a5  mov     dword ptr [rbp+47h+var_80], eax
0x1800838a8  jmp     loc_180083AB1
0x1800838ad  add     rax, 1
0x1800838b1  jz      short loc_1800838C8
0x1800838b3  sub     rax, 1
0x1800838b7  jz      short loc_1800838C8
0x1800838b9  cmp     rax, 1
0x1800838bd  jz      short loc_1800838C8
0x1800838bf  lea     rcx, [rbp+47h+var_80]; void *
0x1800838c3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800838c8  mov     eax, dword ptr [rbp+47h+var_90]
0x1800838cb  mov     dword ptr [rbp+47h+var_80], eax
0x1800838ce  mov     [rbp+47h+var_60], r14b
0x1800838d2  jmp     loc_180083AB1
0x1800838d7  mov     eax, dword ptr [rbp+47h+var_90]
0x1800838da  mov     dword ptr [rbp+47h+var_80], eax
0x1800838dd  mov     [rbp+47h+var_60], r14b
0x1800838e1  jmp     loc_180083993
0x1800838e6  cmp     eax, 0Bh
0x1800838e9  jnz     loc_18008399C
0x1800838ef  mov     qword ptr [rbp+47h+var_90], r14
0x1800838f3  mov     [rbp+47h+pExceptionObject], 8
0x1800838fa  lea     rdx, [rbp+47h+lpSubKey]
0x1800838fe  cmp     [rbp+47h+var_38], 7
0x180083903  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x180083908  lea     rax, [rbp+47h+pExceptionObject]
0x18008390c  mov     [rsp+100h+pcbData], rax; pcbData
0x180083911  lea     rax, [rbp+47h+var_90]
0x180083915  mov     [rsp+100h+pvData], rax; pvData
0x18008391a  lea     rax, [rbp+47h+var_BC]
0x18008391e  mov     [rsp+100h+pdwType], rax; pdwType
0x180083923  mov     r9d, 40h ; '@'; dwFlags
0x180083929  mov     r8, rsi; lpValue
0x18008392c  mov     rcx, rbx; hkey
0x18008392f  call    cs:__imp_RegGetValueW
0x180083935  mov     ebx, eax
0x180083937  test    eax, eax
0x180083939  jnz     loc_180083A90
0x18008393f  cmp     [rbp+47h+var_58], r14b
0x180083943  jz      short loc_180083987
0x180083945  movsx   rax, [rbp+47h+var_60]
0x18008394a  cmp     al, 1
0x18008394c  jnz     short loc_18008395B
0x18008394e  mov     rax, qword ptr [rbp+47h+var_90]
0x180083952  mov     [rbp+47h+var_80], rax
0x180083956  jmp     loc_180083AB1
0x18008395b  add     rax, 1
0x18008395f  jz      short loc_180083976
0x180083961  sub     rax, 1
0x180083965  jz      short loc_180083976
0x180083967  cmp     rax, 1
0x18008396b  jz      short loc_180083976
0x18008396d  lea     rcx, [rbp+47h+var_80]; void *
0x180083971  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180083976  mov     rax, qword ptr [rbp+47h+var_90]
0x18008397a  mov     [rbp+47h+var_80], rax
0x18008397e  mov     [rbp+47h+var_60], 1
0x180083982  jmp     loc_180083AB1
0x180083987  mov     rax, qword ptr [rbp+47h+var_90]
0x18008398b  mov     [rbp+47h+var_80], rax
0x18008398f  mov     [rbp+47h+var_60], 1
0x180083993  mov     [rbp+47h+var_58], 1
0x180083997  jmp     loc_180083AB1
0x18008399c  cmp     eax, 1
0x18008399f  jnz     loc_180083BEB
0x1800839a5  xorps   xmm0, xmm0
0x1800839a8  movups  xmmword ptr [rbp+47h+pExceptionObject], xmm0
0x1800839ac  mov     [rbp+47h+var_A0], r14
0x1800839b0  mov     [rbp+47h+var_98], 7
0x1800839b8  mov     word ptr [rbp+47h+pExceptionObject], r14w
0x1800839bd  mov     edx, [rbp+47h+var_B8]
0x1800839c0  shr     rdx, 1
0x1800839c3  jnz     short loc_1800839D1
0x1800839c5  mov     [rbp+47h+var_A0], rdx
0x1800839c9  mov     word ptr [rbp+rdx*2+47h+pExceptionObject], r14w
0x1800839cf  jmp     short loc_1800839DD
0x1800839d1  xor     r8d, r8d
0x1800839d4  lea     rcx, [rbp+47h+pExceptionObject]; Src
0x1800839d8  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x1800839dd  lea     rax, [rbp+47h+pExceptionObject]
0x1800839e1  cmp     [rbp+47h+var_98], 7
0x1800839e6  cmova   rax, qword ptr [rbp+47h+pExceptionObject]
0x1800839eb  lea     rdx, [rbp+47h+lpSubKey]
0x1800839ef  cmp     [rbp+47h+var_38], 7
0x1800839f4  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x1800839f9  lea     rcx, [rbp+47h+var_B8]
0x1800839fd  mov     [rsp+100h+pcbData], rcx; pcbData
0x180083a02  mov     [rsp+100h+pvData], rax; pvData
0x180083a07  lea     rax, [rbp+47h+var_BC]
0x180083a0b  mov     [rsp+100h+pdwType], rax; pdwType
0x180083a10  mov     r9d, 2; dwFlags
0x180083a16  mov     r8, rsi; lpValue
0x180083a19  mov     rcx, rbx; hkey
0x180083a1c  call    cs:__imp_RegGetValueW
0x180083a22  mov     ebx, eax
0x180083a24  test    eax, eax
0x180083a26  jnz     short loc_180083A87
0x180083a28  jmp     short loc_180083A70
0x180083a2a  lea     rax, [rbp+47h+pExceptionObject]
0x180083a2e  cmp     [rbp+47h+var_98], 7
0x180083a33  cmova   rax, qword ptr [rbp+47h+pExceptionObject]
0x180083a38  lea     rdx, [rcx-1]
0x180083a3c  cmp     [rax+rdx*2], r14w
0x180083a41  jnz     short loc_180083A79
0x180083a43  cmp     rdx, rcx
0x180083a46  ja      short loc_180083A61
0x180083a48  mov     [rbp+47h+var_A0], rdx
0x180083a4c  lea     rax, [rbp+47h+pExceptionObject]
0x180083a50  cmp     [rbp+47h+var_98], 7
0x180083a55  cmova   rax, qword ptr [rbp+47h+pExceptionObject]
0x180083a5a  mov     [rax+rdx*2], r14w
0x180083a5f  jmp     short loc_180083A70
0x180083a61  xor     r8d, r8d
0x180083a64  sub     rdx, rcx
0x180083a67  lea     rcx, [rbp+47h+pExceptionObject]; Src
0x180083a6b  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180083a70  mov     rcx, [rbp+47h+var_A0]
0x180083a74  test    rcx, rcx
0x180083a77  jnz     short loc_180083A2A
0x180083a79  lea     rdx, [rbp+47h+pExceptionObject]
0x180083a7d  lea     rcx, [rbp+47h+var_80]
0x180083a81  call    ??$?4AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@?$optional@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@QEAAAEAV01@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::optional<std::variant<uint,unsigned __int64,std::wstring>>::operator=<std::wstring &,0>(std::wstring &)
0x180083a86  nop
0x180083a87  lea     rcx, [rbp+47h+pExceptionObject]; void *
0x180083a8b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180083a90  cmp     ebx, 2
0x180083a93  jz      loc_180083B6D
0x180083a99  cmp     ebx, 3FAh
0x180083a9f  jz      loc_180083B6D
0x180083aa5  cmp     ebx, 490h
0x180083aab  jz      loc_180083B6D
0x180083ab1  lea     rax, [rbp+47h+lpSubKey]
0x180083ab5  cmp     [rbp+47h+var_38], 7
0x180083aba  cmova   rax, [rbp+47h+lpSubKey]
0x180083abf  mov     rcx, [rbp+4Fh]; this
0x180083ac3  mov     [rsp+100h+pcbData], rsi
0x180083ac8  mov     [rsp+100h+pvData], rax; char *
0x180083acd  mov     [rsp+100h+pdwType], r13; unsigned int
0x180083ad2  mov     r9d, ebx; char *
0x180083ad5  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180083adc  mov     edx, 8Bh; void *
0x180083ae1  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180083ae6  mov     [rdi], r14d
0x180083ae9  lea     rbx, [rdi+8]
0x180083aed  mov     qword ptr [rbp+47h+pExceptionObject], rbx
0x180083af1  mov     [rbx+28h], r14b
0x180083af5  cmp     [rbp+47h+var_58], r14b
0x180083af9  jz      short loc_180083B46
0x180083afb  mov     qword ptr [rbp+47h+var_90], rbx
0x180083aff  mov     byte ptr [rbx+20h], 0FFh
0x180083b03  movsx   rax, [rbp+47h+var_60]
0x180083b08  add     rax, 1
0x180083b0c  jz      short loc_180083B42
0x180083b0e  sub     rax, 1
0x180083b12  jz      short loc_180083B39
0x180083b14  cmp     rax, 1
0x180083b18  jz      short loc_180083B2C
0x180083b1a  lea     rdx, [rbp+47h+var_80]
0x180083b1e  mov     rcx, rbx
0x180083b21  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180083b26  mov     byte ptr [rbx+20h], 2
0x180083b2a  jmp     short loc_180083B42
0x180083b2c  mov     rax, [rbp+47h+var_80]
0x180083b30  mov     [rbx], rax
0x180083b33  mov     byte ptr [rbx+20h], 1
0x180083b37  jmp     short loc_180083B42
0x180083b39  mov     eax, dword ptr [rbp+47h+var_80]
0x180083b3c  mov     [rbx], eax
0x180083b3e  mov     [rbx+20h], r14b
0x180083b42  mov     byte ptr [rbx+28h], 1
0x180083b46  lea     rcx, [rbp+47h+lpSubKey]; void *
0x180083b4a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180083b4f  nop
0x180083b50  cmp     [rbp+47h+var_58], r14b
0x180083b54  jz      short loc_180083BC5
0x180083b56  movsx   rax, [rbp+47h+var_60]
0x180083b5b  add     rax, 1
0x180083b5f  jz      short loc_180083BC5
0x180083b61  sub     rax, 1
0x180083b65  jz      short loc_180083BC5
0x180083b67  cmp     rax, 1
0x180083b6b  jmp     short loc_180083BBA
0x180083b6d  movzx   eax, bx
0x180083b70  or      eax, 80070000h
0x180083b75  test    ebx, ebx
0x180083b77  cmovle  eax, ebx
0x180083b7a  mov     [rdi], eax
0x180083b7c  mov     [rdi+30h], r14b
0x180083b80  jmp     short loc_180083B46
0x180083b82  movzx   eax, dx
0x180083b85  or      eax, 80070000h
0x180083b8a  test    edx, edx
0x180083b8c  cmovle  eax, edx
0x180083b8f  mov     [rdi], eax
0x180083b91  mov     [rdi+30h], r14b
0x180083b95  lea     rcx, [rbp+47h+lpSubKey]; void *
0x180083b99  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180083b9e  nop
0x180083b9f  cmp     [rbp+47h+var_58], r14b
0x180083ba3  jz      short loc_180083BC5
0x180083ba5  movsx   rcx, [rbp+47h+var_60]
0x180083baa  add     rcx, 1
0x180083bae  jz      short loc_180083BC5
0x180083bb0  sub     rcx, 1
0x180083bb4  jz      short loc_180083BC5
0x180083bb6  cmp     rcx, 1
0x180083bba  jz      short loc_180083BC5
0x180083bbc  lea     rcx, [rbp+47h+var_80]; void *
0x180083bc0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180083bc5  mov     rax, rdi
0x180083bc8  mov     rcx, [rbp+47h+var_30]
0x180083bcc  xor     rcx, rsp; StackCookie
0x180083bcf  call    __security_check_cookie
0x180083bd4  mov     rbx, [rsp+100h+arg_0]
  ... truncated ...
```
