# CUpdateService::get_ContentValidationCert(tagVARIANT *)

- ea: `0x180071210`
- end: `0x180071305`
- name: `?get_ContentValidationCert@CUpdateService@@UEAAJPEAUtagVARIANT@@@Z`
- size: `245`
- prototype: `int(CUpdateService *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x180071210`
- `0x18009b050`
- `0x1800a19e0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18007124a`
- `OLEAUT32!__imp_VariantInit` at `0x18007124a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800712e3`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800712e3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18007127e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18007127e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800712ac`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800712ac`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007125e`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007125e`

## string_xrefs

- `0x1800712c2`: `C:\__w\1\s\src\Client\comapi\UpdateService.cpp`

## pseudocode

```c
__int64 __fastcall CUpdateService::get_ContentValidationCert(CUpdateService *this, struct tagVARIANT *a2)
{
  SAFEARRAY *v2; // rdi
  HRESULT v5; // ebx
  __int64 v6; // rdx
  SAFEARRAY *Vector; // rax
  void *ppvData; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = 0;
  ppvData = 0;
  if ( a2 )
  {
    VariantInit(a2);
    Vector = SafeArrayCreateVector(0x11u, 0, *((_DWORD *)this + 76));
    v2 = Vector;
    if ( Vector )
    {
      v5 = SafeArrayAccessData(Vector, &ppvData);
      if ( v5 >= 0 )
      {
        memmove(ppvData, *((const void **)this + 39), *((unsigned int *)this + 76));
        v5 = SafeArrayUnaccessData(v2);
        if ( v5 >= 0 )
        {
          a2->llVal = (LONGLONG)v2;
          v2 = 0;
          v5 = 0;
          a2->vt = 8209;
          goto LABEL_11;
        }
        v6 = 119;
      }
      else
      {
        v6 = 115;
      }
    }
    else
    {
      v5 = -2147024882;
      v6 = 114;
    }
  }
  else
  {
    v5 = -2147467261;
    v6 = 108;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateService.cpp",
    (const char *)(unsigned int)v5,
    (int)ppvData);
LABEL_11:
  SafeArrayDestroy(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180071210  mov     [rsp+arg_10], rbx
0x180071215  push    rbp
0x180071216  push    rsi
0x180071217  push    rdi
0x180071218  sub     rsp, 30h
0x18007121c  mov     rax, cs:__security_cookie
0x180071223  xor     rax, rsp
0x180071226  mov     [rsp+48h+var_20], rax
0x18007122b  xor     edi, edi
0x18007122d  mov     rsi, rdx
0x180071230  mov     [rsp+48h+ppvData], rdi; int
0x180071235  mov     rbp, rcx
0x180071238  test    rdx, rdx
0x18007123b  jnz     short loc_180071247
0x18007123d  mov     ebx, 80004003h
0x180071242  lea     edx, [rsi+6Ch]
0x180071245  jmp     short loc_1800712BD
0x180071247  mov     rcx, rsi; pvarg
0x18007124a  call    cs:__imp_VariantInit
0x180071250  mov     r8d, [rbp+130h]; cElements
0x180071257  mov     ecx, 11h; vt
0x18007125c  xor     edx, edx; lLbound
0x18007125e  call    cs:__imp_SafeArrayCreateVector
0x180071264  mov     rdi, rax
0x180071267  test    rax, rax
0x18007126a  jnz     short loc_180071276
0x18007126c  mov     ebx, 8007000Eh
0x180071271  lea     edx, [rax+72h]
0x180071274  jmp     short loc_1800712BD
0x180071276  lea     rdx, [rsp+48h+ppvData]; ppvData
0x18007127b  mov     rcx, rdi; psa
0x18007127e  call    cs:__imp_SafeArrayAccessData
0x180071284  mov     ebx, eax
0x180071286  test    eax, eax
0x180071288  jns     short loc_180071291
0x18007128a  mov     edx, 73h ; 's'
0x18007128f  jmp     short loc_1800712BD
0x180071291  mov     r8d, [rbp+130h]; Size
0x180071298  mov     rdx, [rbp+138h]; Src
0x18007129f  mov     rcx, [rsp+48h+ppvData]; void *
0x1800712a4  call    memmove
0x1800712a9  mov     rcx, rdi; psa
0x1800712ac  call    cs:__imp_SafeArrayUnaccessData
0x1800712b2  mov     ebx, eax
0x1800712b4  test    eax, eax
0x1800712b6  jns     short loc_1800712D3
0x1800712b8  mov     edx, 77h ; 'w'; void *
0x1800712bd  mov     rcx, [rsp+48h]; this
0x1800712c2  lea     r8, aCW1SSrcClientC_66; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x1800712c9  mov     r9d, ebx; char *
0x1800712cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800712d1  jmp     short loc_1800712E0
0x1800712d3  mov     [rsi+8], rdi
0x1800712d7  xor     edi, edi
0x1800712d9  xor     ebx, ebx
0x1800712db  mov     word ptr [rsi], 2011h
0x1800712e0  mov     rcx, rdi; psa
0x1800712e3  call    cs:__imp_SafeArrayDestroy
0x1800712e9  mov     eax, ebx
0x1800712eb  mov     rcx, [rsp+48h+var_20]
0x1800712f0  xor     rcx, rsp; StackCookie
0x1800712f3  call    __security_check_cookie
0x1800712f8  mov     rbx, [rsp+48h+arg_10]
0x1800712fd  add     rsp, 30h
0x180071301  pop     rdi
0x180071302  pop     rsi
0x180071303  pop     rbp
0x180071304  retn
```
