# CExternalBase::RemoveFromPersistentStore(IWbemServices *,_SECURITY_PRODUCT_TYPE)

- ea: `0x180037a0c`
- end: `0x180037c2c`
- name: `?RemoveFromPersistentStore@CExternalBase@@QEAAJPEAUIWbemServices@@W4_SECURITY_PRODUCT_TYPE@@@Z`
- size: `544`
- prototype: `int(CExternalBase *__hidden this, struct IWbemServices *, enum _SECURITY_PRODUCT_TYPE)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800250c0`
- `0x180036adc`

## callees

- `0x180008e48`
- `0x180016ae8`
- `0x18001f97c`
- `0x1800202e8`
- `0x1800287b0`
- `0x1800296d4`
- `0x180037a0c`
- `0x18003fbf2`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180037b46`
- `OLEAUT32!__imp_SysAllocString` at `0x180037b91`
- `OLEAUT32!__imp_SysAllocString` at `0x180037b46`
- `OLEAUT32!__imp_SysAllocString` at `0x180037b91`
- `OLEAUT32!__imp_SysFreeString` at `0x180037bfd`
- `OLEAUT32!__imp_SysFreeString` at `0x180037c06`
- `OLEAUT32!__imp_SysFreeString` at `0x180037bfd`
- `OLEAUT32!__imp_SysFreeString` at `0x180037c06`
- `ADVAPI32!RegDeleteKeyW` at `0x180037ae1`
- `ADVAPI32!RegDeleteKeyW` at `0x180037ae1`

## string_xrefs

- `0x180037abc`: `admin\wsc\src\client\service\wscsvclib\externalbase.cpp`

## pseudocode

```c
__int64 __fastcall CExternalBase::RemoveFromPersistentStore(
        CExternalBase *this,
        struct IWbemServices *a2,
        enum _SECURITY_PRODUCT_TYPE a3)
{
  const unsigned __int16 *DatastoreRegKey; // rbx
  int v7; // eax
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  const OLECHAR *v10; // rax
  OLECHAR *v11; // rbp
  OLECHAR *v12; // rsi
  int v13; // eax
  int v14[2]; // [rsp+20h] [rbp-468h]
  WCHAR SubKey[264]; // [rsp+30h] [rbp-458h] BYREF
  OLECHAR psz[264]; // [rsp+240h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+0h]

  DatastoreRegKey = WscGetDatastoreRegKey(a3);
  if ( DatastoreRegKey )
  {
    memset_0(SubKey, 0, 0x208u);
    *(_QWORD *)v14 = *((_QWORD *)this + 1);
    v7 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", DatastoreRegKey);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v9 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
      if ( v9
        && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids,
          (unsigned int)SubKey,
          v9);
      }
      memset_0(psz, 0, 0x208u);
      v10 = (const OLECHAR *)(*(__int64 (__fastcall **)(CExternalBase *))(*(_QWORD *)this + 16LL))(this);
      v11 = SysAllocString(v10);
      if ( v11 )
      {
        v8 = StringCchPrintfW(psz, 0x104u, L"%s.instanceGuid=\"%s\"", v11, *((_QWORD *)this + 1));
        if ( !v8 )
        {
          v12 = SysAllocString(psz);
          if ( v12 )
          {
            v13 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->DeleteInstance)(
                    a2,
                    v12,
                    0,
                    0,
                    0);
            v8 = v13;
            if ( v13 < 0
              && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                14,
                WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids,
                (unsigned int)v13);
            }
            SysFreeString(v12);
          }
          else
          {
            v8 = -2147024882;
          }
        }
        SysFreeString(v11);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x288,
        (unsigned int)"admin\\wsc\\src\\client\\service\\wscsvclib\\externalbase.cpp",
        (const char *)(unsigned int)v7,
        v14[0]);
    }
    return v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids);
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180037a0c  push    rbx
0x180037a0e  push    rbp
0x180037a0f  push    rsi
0x180037a10  push    rdi
0x180037a11  push    r14
0x180037a13  sub     rsp, 460h
0x180037a1a  mov     rax, cs:__security_cookie
0x180037a21  xor     rax, rsp
0x180037a24  mov     [rsp+488h+var_38], rax
0x180037a2c  mov     rsi, rcx
0x180037a2f  mov     r14, rdx
0x180037a32  mov     ecx, r8d; enum _SECURITY_PRODUCT_TYPE
0x180037a35  call    ?WscGetDatastoreRegKey@@YAPEBGW4_SECURITY_PRODUCT_TYPE@@@Z; WscGetDatastoreRegKey(_SECURITY_PRODUCT_TYPE)
0x180037a3a  mov     rbx, rax
0x180037a3d  test    rax, rax
0x180037a40  jnz     short loc_180037A78
0x180037a42  mov     rcx, cs:WPP_GLOBAL_Control
0x180037a49  lea     rdi, WPP_GLOBAL_Control
0x180037a50  cmp     rcx, rdi
0x180037a53  jz      short loc_180037A6E
0x180037a55  test    byte ptr [rcx+1Ch], 1
0x180037a59  jz      short loc_180037A6E
0x180037a5b  mov     rcx, [rcx+10h]
0x180037a5f  lea     edx, [rax+0Ch]
0x180037a62  lea     r8, WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids
0x180037a69  call    WPP_SF_
0x180037a6e  mov     eax, 80004005h
0x180037a73  jmp     loc_180037C0E
0x180037a78  mov     ebp, 208h
0x180037a7d  lea     rcx, [rsp+488h+SubKey]; void *
0x180037a82  mov     r8d, ebp; Size
0x180037a85  xor     edx, edx; Val
0x180037a87  call    memset_0
0x180037a8c  mov     rax, [rsi+8]
0x180037a90  lea     r8, aSS; "%s\\%s"
0x180037a97  mov     r9, rbx
0x180037a9a  mov     qword ptr [rsp+488h+var_468], rax; int
0x180037a9f  mov     edx, 104h; unsigned __int64
0x180037aa4  lea     rcx, [rsp+488h+SubKey]; unsigned __int16 *
0x180037aa9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037aae  mov     ebx, eax
0x180037ab0  test    eax, eax
0x180037ab2  jns     short loc_180037AD5
0x180037ab4  mov     rcx, [rsp+488h]; this
0x180037abc  lea     r8, aAdminWscSrcCli_0; "admin\\wsc\\src\\client\\service\\wscsv"...
0x180037ac3  mov     r9d, eax; char *
0x180037ac6  mov     edx, 288h; void *
0x180037acb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037ad0  jmp     loc_180037C0C
0x180037ad5  lea     rdx, [rsp+488h+SubKey]; lpSubKey
0x180037ada  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037ae1  call    cs:__imp_RegDeleteKeyW
0x180037ae7  lea     rdi, WPP_GLOBAL_Control
0x180037aee  test    eax, eax
0x180037af0  jz      short loc_180037B22
0x180037af2  mov     rcx, cs:WPP_GLOBAL_Control
0x180037af9  cmp     rcx, rdi
0x180037afc  jz      short loc_180037B22
0x180037afe  test    byte ptr [rcx+1Ch], 1
0x180037b02  jz      short loc_180037B22
0x180037b04  mov     rcx, [rcx+10h]
0x180037b08  lea     r9, [rsp+488h+SubKey]
0x180037b0d  mov     edx, 0Dh
0x180037b12  mov     [rsp+488h+var_468], eax
0x180037b16  lea     r8, WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids
0x180037b1d  call    WPP_SF_Sd
0x180037b22  mov     r8, rbp; Size
0x180037b25  lea     rcx, [rsp+488h+psz]; void *
0x180037b2d  xor     edx, edx; Val
0x180037b2f  call    memset_0
0x180037b34  mov     rax, [rsi]
0x180037b37  mov     rcx, rsi
0x180037b3a  mov     rax, [rax+10h]
0x180037b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b43  mov     rcx, rax; psz
0x180037b46  call    cs:__imp_SysAllocString
0x180037b4c  mov     rbp, rax
0x180037b4f  test    rax, rax
0x180037b52  jnz     short loc_180037B5E
0x180037b54  mov     ebx, 8007000Eh
0x180037b59  jmp     loc_180037C0C
0x180037b5e  mov     rax, [rsi+8]
0x180037b62  lea     r8, aSInstanceguidS; "%s.instanceGuid=\"%s\""
0x180037b69  mov     r9, rbp
0x180037b6c  mov     qword ptr [rsp+488h+var_468], rax
0x180037b71  mov     edx, 104h; unsigned __int64
0x180037b76  lea     rcx, [rsp+488h+psz]; unsigned __int16 *
0x180037b7e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037b83  mov     ebx, eax
0x180037b85  test    eax, eax
0x180037b87  jnz     short loc_180037C03
0x180037b89  lea     rcx, [rsp+488h+psz]; psz
0x180037b91  call    cs:__imp_SysAllocString
0x180037b97  mov     rsi, rax
0x180037b9a  test    rax, rax
0x180037b9d  jnz     short loc_180037BA6
0x180037b9f  mov     ebx, 8007000Eh
0x180037ba4  jmp     short loc_180037C03
0x180037ba6  mov     rax, [r14]
0x180037ba9  xor     r9d, r9d
0x180037bac  xor     r8d, r8d
0x180037baf  mov     qword ptr [rsp+488h+var_468], 0
0x180037bb8  mov     rdx, rsi
0x180037bbb  mov     rcx, r14
0x180037bbe  mov     rax, [rax+80h]
0x180037bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037bca  mov     ebx, eax
0x180037bcc  test    eax, eax
0x180037bce  jns     short loc_180037BFA
0x180037bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180037bd7  cmp     rcx, rdi
0x180037bda  jz      short loc_180037BFA
0x180037bdc  test    byte ptr [rcx+1Ch], 1
0x180037be0  jz      short loc_180037BFA
0x180037be2  mov     rcx, [rcx+10h]
0x180037be6  lea     r8, WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids
0x180037bed  mov     edx, 0Eh
0x180037bf2  mov     r9d, eax
0x180037bf5  call    WPP_SF_d
0x180037bfa  mov     rcx, rsi; bstrString
0x180037bfd  call    cs:__imp_SysFreeString
0x180037c03  mov     rcx, rbp; bstrString
0x180037c06  call    cs:__imp_SysFreeString
0x180037c0c  mov     eax, ebx
0x180037c0e  mov     rcx, [rsp+488h+var_38]
0x180037c16  xor     rcx, rsp; StackCookie
0x180037c19  call    __security_check_cookie
0x180037c1e  add     rsp, 460h
0x180037c25  pop     r14
0x180037c27  pop     rdi
0x180037c28  pop     rsi
0x180037c29  pop     rbp
0x180037c2a  pop     rbx
0x180037c2b  retn
```
