# CAzureAttestationUtils::CrackUri(IMemObj *,void const *,void * *,void * *,ulong *,ulong *,bool *)

- ea: `0x10082bd70`
- end: `0x10082bf92`
- name: `?CrackUri@CAzureAttestationUtils@@SAJPEAVIMemObj@@PEBXPEAPEAX2PEAK3PEA_N@Z`
- size: `546`
- prototype: `static int(struct IMemObj *, const void *, void **, void **, unsigned int *, unsigned int *, bool *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10082cb80`
- `0x10082e560`

## callees

- `0x10082bd70`

## import_xrefs

- `urlmon!CreateUri` at `0x10082bdbc`
- `urlmon!CreateUri` at `0x10082bdbc`
- `ole32!CoUninitialize` at `0x10082bf6b`
- `ole32!CoUninitialize` at `0x10082bf6b`
- `ole32!CoInitialize` at `0x10082bd92`
- `ole32!CoInitialize` at `0x10082bd92`
- `OLEAUT32!__imp_SysFreeString` at `0x10082be4d`
- `OLEAUT32!__imp_SysFreeString` at `0x10082bec5`
- `OLEAUT32!__imp_SysFreeString` at `0x10082bf65`
- `OLEAUT32!__imp_SysFreeString` at `0x10082be4d`
- `OLEAUT32!__imp_SysFreeString` at `0x10082bec5`
- `OLEAUT32!__imp_SysFreeString` at `0x10082bf65`
- `OLEAUT32!__imp_SysStringLen` at `0x10082bdf4`
- `OLEAUT32!__imp_SysStringLen` at `0x10082be79`
- `OLEAUT32!__imp_SysStringLen` at `0x10082bdf4`
- `OLEAUT32!__imp_SysStringLen` at `0x10082be79`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082be26`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082bea4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082be26`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082bea4`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10082bf4b`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10082bf4b`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x10082be3f`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x10082beba`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x10082be3f`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x10082beba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall CAzureAttestationUtils::CrackUri(
        struct IMemObj *a1,
        const WCHAR *a2,
        void **a3,
        void **a4,
        unsigned int *a5,
        unsigned int *a6,
        bool *a7)
{
  HRESULT result; // eax
  HRESULT v12; // ebx
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rax
  void *v15; // rax
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rax
  void *v18; // rax
  int v19; // eax
  BSTR S2; // [rsp+78h] [rbp+10h] BYREF
  IUri *ppURI; // [rsp+80h] [rbp+18h] BYREF
  BSTR pbstr; // [rsp+88h] [rbp+20h] BYREF

  result = CoInitialize(0);
  if ( result >= 0 )
  {
    ppURI = 0;
    v12 = CreateUri(a2, 0, 0, &ppURI);
    if ( v12 >= 0 )
    {
      v12 = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetHost)(ppURI, &pbstr);
      if ( v12 >= 0 )
      {
        v13 = SysStringLen(pbstr) + 1;
        v14 = 2 * v13;
        if ( !is_mul_ok(v13, 2u) )
          v14 = -1;
        v15 = operator new[](v14, a1, "Sql\\Ntdbms\\aetmhost\\AzureAttestationUtils.cpp", 54, 6u);
        *a3 = v15;
        wmemcpy_s((wchar_t *)v15, (unsigned int)v13, pbstr, (unsigned int)v13);
        SysFreeString(pbstr);
        v12 = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetPathAndQuery)(ppURI, &S2);
        if ( v12 >= 0 )
        {
          v16 = SysStringLen(S2) + 1;
          v17 = 2 * v16;
          if ( !is_mul_ok(v16, 2u) )
            v17 = -1;
          v18 = operator new[](v17, a1, "Sql\\Ntdbms\\aetmhost\\AzureAttestationUtils.cpp", 67, 6u);
          *a4 = v18;
          wmemcpy_s((wchar_t *)v18, (unsigned int)v16, S2, (unsigned int)v16);
          SysFreeString(S2);
          v12 = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetPort)(ppURI, &S2);
          if ( v12 >= 0 )
          {
            *a5 = (unsigned int)S2;
            v12 = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetScheme)(ppURI, &S2);
            if ( v12 >= 0 )
            {
              *a6 = (unsigned int)S2;
              v12 = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetQuery)(ppURI, &S2);
              if ( v12 >= 0 )
              {
                v19 = _wcsicmp(L"?api-version=2018-09-01-preview", S2);
                *a7 = v19 == 0;
              }
              SysFreeString(S2);
            }
          }
        }
      }
    }
    CoUninitialize();
    if ( ppURI )
      ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x10082bd70  push    rbx
0x10082bd72  push    rbp
0x10082bd73  push    rsi
0x10082bd74  push    rdi
0x10082bd75  push    r14
0x10082bd77  sub     rsp, 40h
0x10082bd7b  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x10082bd84  mov     r14, r9
0x10082bd87  mov     rsi, r8
0x10082bd8a  mov     rbx, rdx
0x10082bd8d  mov     rdi, rcx
0x10082bd90  xor     ecx, ecx; pvReserved
0x10082bd92  call    cs:__imp_CoInitialize
0x10082bd98  test    eax, eax
0x10082bd9a  js      loc_10082BF87
0x10082bda0  mov     [rsp+68h+ppURI], 0
0x10082bdac  lea     r9, [rsp+68h+ppURI]; ppURI
0x10082bdb4  xor     r8d, r8d; dwReserved
0x10082bdb7  xor     edx, edx; dwFlags
0x10082bdb9  mov     rcx, rbx; pwzURI
0x10082bdbc  call    cs:__imp_CreateUri
0x10082bdc2  mov     ebx, eax
0x10082bdc4  test    eax, eax
0x10082bdc6  js      loc_10082BF6B
0x10082bdcc  mov     rcx, [rsp+68h+ppURI]
0x10082bdd4  mov     rax, [rcx]
0x10082bdd7  lea     rdx, [rsp+68h+pbstr]
0x10082bddf  call    qword ptr [rax+68h]
0x10082bde2  mov     ebx, eax
0x10082bde4  test    eax, eax
0x10082bde6  js      loc_10082BF6B
0x10082bdec  mov     rcx, [rsp+68h+pbstr]; pbstr
0x10082bdf4  call    cs:__imp_SysStringLen
0x10082bdfa  lea     ebx, [rax+1]
0x10082bdfd  mov     eax, 2
0x10082be02  mul     rbx
0x10082be05  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x10082be0c  cmovo   rax, rbp
0x10082be10  mov     [rsp+68h+var_48], 6
0x10082be15  lea     r9d, [rbp+37h]
0x10082be19  lea     r8, aSqlNtdbmsAetmh_0; "Sql\\Ntdbms\\aetmhost\\AzureAttestation"...
0x10082be20  mov     rdx, rdi
0x10082be23  mov     rcx, rax
0x10082be26  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10082be2c  mov     [rsi], rax
0x10082be2f  mov     r9d, ebx; N
0x10082be32  mov     r8, [rsp+68h+pbstr]; S2
0x10082be3a  mov     edx, ebx; N1
0x10082be3c  mov     rcx, rax; S1
0x10082be3f  call    cs:__imp_wmemcpy_s
0x10082be45  mov     rcx, [rsp+68h+pbstr]; bstrString
0x10082be4d  call    cs:__imp_SysFreeString
0x10082be53  mov     rcx, [rsp+68h+ppURI]
0x10082be5b  mov     r8, [rcx]
0x10082be5e  lea     rdx, [rsp+68h+S2]
0x10082be63  call    qword ptr [r8+80h]
0x10082be6a  mov     ebx, eax
0x10082be6c  test    eax, eax
0x10082be6e  js      loc_10082BF6B
0x10082be74  mov     rcx, [rsp+68h+S2]; pbstr
0x10082be79  call    cs:__imp_SysStringLen
0x10082be7f  lea     ebx, [rax+1]
0x10082be82  mov     eax, 2
0x10082be87  mul     rbx
0x10082be8a  cmovo   rax, rbp
0x10082be8e  mov     [rsp+68h+var_48], 6
0x10082be93  lea     r9d, [rbp+44h]
0x10082be97  lea     r8, aSqlNtdbmsAetmh_0; "Sql\\Ntdbms\\aetmhost\\AzureAttestation"...
0x10082be9e  mov     rdx, rdi
0x10082bea1  mov     rcx, rax
0x10082bea4  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10082beaa  mov     [r14], rax
0x10082bead  mov     r9d, ebx; N
0x10082beb0  mov     r8, [rsp+68h+S2]; S2
0x10082beb5  mov     edx, ebx; N1
0x10082beb7  mov     rcx, rax; S1
0x10082beba  call    cs:__imp_wmemcpy_s
0x10082bec0  mov     rcx, [rsp+68h+S2]; bstrString
0x10082bec5  call    cs:__imp_SysFreeString
0x10082becb  mov     rcx, [rsp+68h+ppURI]
0x10082bed3  mov     rax, [rcx]
0x10082bed6  lea     rdx, [rsp+68h+S2]
0x10082bedb  call    qword ptr [rax+0B8h]
0x10082bee1  mov     ebx, eax
0x10082bee3  test    eax, eax
0x10082bee5  js      loc_10082BF6B
0x10082beeb  mov     rcx, [rsp+68h+arg_20]
0x10082bef3  mov     eax, dword ptr [rsp+68h+S2]
0x10082bef7  mov     [rcx], eax
0x10082bef9  mov     rcx, [rsp+68h+ppURI]
0x10082bf01  mov     rax, [rcx]
0x10082bf04  lea     rdx, [rsp+68h+S2]
0x10082bf09  call    qword ptr [rax+0C0h]
0x10082bf0f  mov     ebx, eax
0x10082bf11  test    eax, eax
0x10082bf13  js      short loc_10082BF6B
0x10082bf15  mov     rcx, [rsp+68h+arg_28]
0x10082bf1d  mov     eax, dword ptr [rsp+68h+S2]
0x10082bf21  mov     [rcx], eax
0x10082bf23  mov     rcx, [rsp+68h+ppURI]
0x10082bf2b  mov     rax, [rcx]
0x10082bf2e  lea     rdx, [rsp+68h+S2]
0x10082bf33  call    qword ptr [rax+88h]
0x10082bf39  mov     ebx, eax
0x10082bf3b  test    eax, eax
0x10082bf3d  js      short loc_10082BF60
0x10082bf3f  mov     rdx, [rsp+68h+S2]; String2
0x10082bf44  lea     rcx, aApiVersion2018; "?api-version=2018-09-01-preview"
0x10082bf4b  call    cs:__imp__wcsicmp
0x10082bf51  test    eax, eax
0x10082bf53  setz    cl
0x10082bf56  mov     rax, [rsp+68h+arg_30]
0x10082bf5e  mov     [rax], cl
0x10082bf60  mov     rcx, [rsp+68h+S2]; bstrString
0x10082bf65  call    cs:__imp_SysFreeString
0x10082bf6b  call    cs:__imp_CoUninitialize
0x10082bf71  nop
0x10082bf72  mov     rcx, [rsp+68h+ppURI]
0x10082bf7a  test    rcx, rcx
0x10082bf7d  jz      short loc_10082BF85
0x10082bf7f  mov     rax, [rcx]
0x10082bf82  call    qword ptr [rax+10h]
0x10082bf85  mov     eax, ebx
0x10082bf87  add     rsp, 40h
0x10082bf8b  pop     r14
0x10082bf8d  pop     rdi
0x10082bf8e  pop     rsi
0x10082bf8f  pop     rbp
0x10082bf90  pop     rbx
0x10082bf91  retn
```
