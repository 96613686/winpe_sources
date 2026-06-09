# CSWbemNamedValue::get_Name(ushort * *)

- ea: `0x180014870`
- end: `0x18001497e`
- name: `?get_Name@CSWbemNamedValue@@UEAAJPEAPEAG@Z`
- size: `270`
- prototype: `__int64 __fastcall(CSWbemNamedValue *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180006300`
- `0x180014870`
- `0x180014984`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800148c3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800148c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800148ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800148ef`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014965`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014965`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800148a1`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800148a1`

## pseudocode

```c
__int64 __fastcall CSWbemNamedValue::get_Name(const OLECHAR **this, unsigned __int16 **a2)
{
  unsigned int v4; // edi
  unsigned __int16 *v6; // rbx
  ICreateErrorInfo *pperrinfo; // [rsp+38h] [rbp+10h] BYREF
  IErrorInfo *perrinfo; // [rsp+40h] [rbp+18h] BYREF

  ResetLastErrors();
  if ( a2 )
  {
    v4 = 0;
    *a2 = SysAllocString(this[15]);
  }
  else
  {
    v4 = -2147217400;
    pperrinfo = 0;
    *((_DWORD *)this + 14) = -2147217400;
    if ( CreateErrorInfo(&pperrinfo) >= 0 )
    {
      v6 = MapHresultToWmiDescription(0x80041008);
      ((void (__fastcall *)(ICreateErrorInfo *, unsigned __int16 *))pperrinfo->lpVtbl->SetDescription)(pperrinfo, v6);
      SysFreeString(v6);
      ((void (__fastcall *)(ICreateErrorInfo *, const OLECHAR **))pperrinfo->lpVtbl->SetGUID)(pperrinfo, this + 13);
      ((void (__fastcall *)(ICreateErrorInfo *, const OLECHAR *))pperrinfo->lpVtbl->SetSource)(pperrinfo, this[6]);
      perrinfo = 0;
      if ( ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
             pperrinfo,
             &IID_IErrorInfo,
             &perrinfo) >= 0 )
      {
        SetErrorInfo(0, perrinfo);
        ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
      }
      ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180014870  mov     [rsp+arg_0], rbx
0x180014875  mov     [rsp+arg_18], rsi
0x18001487a  push    rdi
0x18001487b  sub     rsp, 20h
0x18001487f  mov     rbx, rdx
0x180014882  mov     rsi, rcx
0x180014885  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18001488a  test    rbx, rbx
0x18001488d  jnz     short loc_1800148BD
0x18001488f  mov     edi, 80041008h
0x180014894  mov     [rsp+28h+pperrinfo], rbx
0x180014899  lea     rcx, [rsp+28h+pperrinfo]; pperrinfo
0x18001489e  mov     [rsi+38h], edi
0x1800148a1  call    cs:__imp_CreateErrorInfo
0x1800148a7  test    eax, eax
0x1800148a9  jns     short loc_1800148CE
0x1800148ab  mov     rbx, [rsp+28h+arg_0]
0x1800148b0  mov     eax, edi
0x1800148b2  mov     rsi, [rsp+28h+arg_18]
0x1800148b7  add     rsp, 20h
0x1800148bb  pop     rdi
0x1800148bc  retn
0x1800148bd  mov     rcx, [rsi+78h]; psz
0x1800148c1  xor     edi, edi
0x1800148c3  call    cs:__imp_SysAllocString
0x1800148c9  mov     [rbx], rax
0x1800148cc  jmp     short loc_1800148AB
0x1800148ce  mov     ecx, edi; int
0x1800148d0  call    ?MapHresultToWmiDescription@@YAPEAGJ@Z; MapHresultToWmiDescription(long)
0x1800148d5  mov     rcx, [rsp+28h+pperrinfo]
0x1800148da  mov     rbx, rax
0x1800148dd  mov     rdx, [rcx]
0x1800148e0  mov     rax, [rdx+28h]
0x1800148e4  mov     rdx, rbx
0x1800148e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148ec  mov     rcx, rbx; bstrString
0x1800148ef  call    cs:__imp_SysFreeString
0x1800148f5  mov     rcx, [rsp+28h+pperrinfo]
0x1800148fa  lea     rdx, [rsi+68h]
0x1800148fe  mov     rax, [rcx]
0x180014901  mov     rax, [rax+18h]
0x180014905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001490a  mov     rcx, [rsp+28h+pperrinfo]
0x18001490f  mov     rdx, [rsi+30h]
0x180014913  mov     rax, [rcx]
0x180014916  mov     rax, [rax+20h]
0x18001491a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001491f  mov     rcx, [rsp+28h+pperrinfo]
0x180014924  lea     r8, [rsp+28h+perrinfo]
0x180014929  mov     [rsp+28h+perrinfo], 0
0x180014932  lea     rdx, IID_IErrorInfo
0x180014939  mov     rax, [rcx]
0x18001493c  mov     rax, [rax]
0x18001493f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014944  test    eax, eax
0x180014946  jns     short loc_18001495E
0x180014948  mov     rcx, [rsp+28h+pperrinfo]
0x18001494d  mov     rax, [rcx]
0x180014950  mov     rax, [rax+10h]
0x180014954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014959  jmp     loc_1800148AB
0x18001495e  mov     rdx, [rsp+28h+perrinfo]; perrinfo
0x180014963  xor     ecx, ecx; dwReserved
0x180014965  call    cs:__imp_SetErrorInfo
0x18001496b  mov     rcx, [rsp+28h+perrinfo]
0x180014970  mov     rax, [rcx]
0x180014973  mov     rax, [rax+10h]
0x180014977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001497c  jmp     short loc_180014948
```
