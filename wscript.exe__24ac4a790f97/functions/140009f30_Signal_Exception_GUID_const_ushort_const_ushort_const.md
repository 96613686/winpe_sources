# Signal_Exception(_GUID const &,ushort const *,ushort const *,...)

- ea: `0x140009f30`
- end: `0x14000a091`
- name: `?Signal_Exception@@YAJAEBU_GUID@@PEBG1ZZ`
- size: `353`
- prototype: `__int64(const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f2f0`

## callees

- `0x140009cf0`
- `0x140009f30`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000a07e`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a07e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14000a049`
- `OLEAUT32!__imp_SetErrorInfo` at `0x14000a049`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x140009f6f`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x140009f6f`

## pseudocode

```c
__int64 Signal_Exception(const struct _GUID *a1, const unsigned __int16 *a2, const unsigned __int16 *a3, ...)
{
  unsigned __int16 *v4; // rdi
  HRESULT v6; // ebx
  ICreateErrorInfo *pperrinfo; // [rsp+20h] [rbp-20h] BYREF
  char *v9; // [rsp+28h] [rbp-18h] BYREF
  IErrorInfo *perrinfo; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v11; // [rsp+38h] [rbp-8h] BYREF
  va_list va; // [rsp+88h] [rbp+48h] BYREF

  va_start(va, a3);
  v9 = 0;
  v4 = 0;
  perrinfo = 0;
  v11 = 0;
  pperrinfo = 0;
  v6 = CreateErrorInfo(&pperrinfo);
  if ( v6 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const struct _GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, a1);
    if ( v6 >= 0 )
    {
      v6 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))pperrinfo->lpVtbl->SetSource)(
             pperrinfo,
             a2);
      if ( v6 >= 0 )
      {
        va_copy(v9, va);
        FormatLine(a3, &v11, &v9);
        v9 = 0;
        v4 = v11;
        v6 = ((__int64 (__fastcall *)(ICreateErrorInfo *, unsigned __int16 *))pperrinfo->lpVtbl->SetDescription)(
               pperrinfo,
               v11);
        if ( v6 >= 0 )
        {
          v6 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetHelpFile)(pperrinfo, 0);
          if ( v6 >= 0 )
          {
            v6 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetHelpContext)(pperrinfo, 0);
            if ( v6 >= 0 )
            {
              v6 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
                     pperrinfo,
                     &IID_IErrorInfo,
                     &perrinfo);
              if ( v6 >= 0 )
                v6 = SetErrorInfo(0, perrinfo);
            }
          }
        }
      }
    }
  }
  if ( pperrinfo )
    ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  if ( perrinfo )
    ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
  SysFreeString(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140009f30  mov     [rsp-28h+lpWideCharStr], r8
0x140009f35  mov     [rsp-28h+arg_18], r9
0x140009f3a  push    rbp
0x140009f3b  push    rbx
0x140009f3c  push    rsi
0x140009f3d  push    rdi
0x140009f3e  push    r14
0x140009f40  mov     rbp, rsp
0x140009f43  sub     rsp, 40h
0x140009f47  mov     rsi, rcx
0x140009f4a  mov     [rbp+var_18], 0
0x140009f52  xor     edi, edi
0x140009f54  mov     [rbp+perrinfo], 0
0x140009f5c  lea     rcx, [rbp+pperrinfo]; pperrinfo
0x140009f60  mov     [rbp+var_8], rdi
0x140009f64  mov     r14, rdx
0x140009f67  mov     [rbp+pperrinfo], 0
0x140009f6f  call    cs:__imp_CreateErrorInfo
0x140009f75  mov     ebx, eax
0x140009f77  test    eax, eax
0x140009f79  js      loc_14000A051
0x140009f7f  mov     rcx, [rbp+pperrinfo]
0x140009f83  mov     rdx, rsi
0x140009f86  mov     rax, [rcx]
0x140009f89  mov     rax, [rax+18h]
0x140009f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f92  mov     ebx, eax
0x140009f94  test    eax, eax
0x140009f96  js      loc_14000A051
0x140009f9c  mov     rcx, [rbp+pperrinfo]
0x140009fa0  mov     rdx, r14
0x140009fa3  mov     rax, [rcx]
0x140009fa6  mov     rax, [rax+20h]
0x140009faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009faf  mov     ebx, eax
0x140009fb1  test    eax, eax
0x140009fb3  js      loc_14000A051
0x140009fb9  mov     rcx, [rbp+lpWideCharStr]; lpWideCharStr
0x140009fbd  lea     rax, [rbp+arg_18]
0x140009fc1  lea     r8, [rbp+var_18]; char **
0x140009fc5  mov     [rbp+var_18], rax
0x140009fc9  lea     rdx, [rbp+var_8]; unsigned __int16 **
0x140009fcd  call    ?FormatLine@@YAJPEBGPEAPEAGPEAPEAD@Z; FormatLine(ushort const *,ushort * *,char * *)
0x140009fd2  mov     rcx, [rbp+pperrinfo]
0x140009fd6  mov     [rbp+var_18], rdi
0x140009fda  mov     rdi, [rbp+var_8]
0x140009fde  mov     rdx, rdi
0x140009fe1  mov     rax, [rcx]
0x140009fe4  mov     rax, [rax+28h]
0x140009fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009fed  mov     ebx, eax
0x140009fef  test    eax, eax
0x140009ff1  js      short loc_14000A051
0x140009ff3  mov     rcx, [rbp+pperrinfo]
0x140009ff7  xor     edx, edx
0x140009ff9  mov     rax, [rcx]
0x140009ffc  mov     rax, [rax+30h]
0x14000a000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a005  mov     ebx, eax
0x14000a007  test    eax, eax
0x14000a009  js      short loc_14000A051
0x14000a00b  mov     rcx, [rbp+pperrinfo]
0x14000a00f  xor     edx, edx
0x14000a011  mov     rax, [rcx]
0x14000a014  mov     rax, [rax+38h]
0x14000a018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a01d  mov     ebx, eax
0x14000a01f  test    eax, eax
0x14000a021  js      short loc_14000A051
0x14000a023  mov     rcx, [rbp+pperrinfo]
0x14000a027  lea     r8, [rbp+perrinfo]
0x14000a02b  lea     rdx, IID_IErrorInfo
0x14000a032  mov     rax, [rcx]
0x14000a035  mov     rax, [rax]
0x14000a038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a03d  mov     ebx, eax
0x14000a03f  test    eax, eax
0x14000a041  js      short loc_14000A051
0x14000a043  mov     rdx, [rbp+perrinfo]; perrinfo
0x14000a047  xor     ecx, ecx; dwReserved
0x14000a049  call    cs:__imp_SetErrorInfo
0x14000a04f  mov     ebx, eax
0x14000a051  mov     rcx, [rbp+pperrinfo]
0x14000a055  test    rcx, rcx
0x14000a058  jz      short loc_14000A066
0x14000a05a  mov     rax, [rcx]
0x14000a05d  mov     rax, [rax+10h]
0x14000a061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a066  mov     rcx, [rbp+perrinfo]
0x14000a06a  test    rcx, rcx
0x14000a06d  jz      short loc_14000A07B
0x14000a06f  mov     rax, [rcx]
0x14000a072  mov     rax, [rax+10h]
0x14000a076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a07b  mov     rcx, rdi; bstrString
0x14000a07e  call    cs:__imp_SysFreeString
0x14000a084  mov     eax, ebx
0x14000a086  add     rsp, 40h
0x14000a08a  pop     r14
0x14000a08c  pop     rdi
0x14000a08d  pop     rsi
0x14000a08e  pop     rbx
0x14000a08f  pop     rbp
0x14000a090  retn
```
