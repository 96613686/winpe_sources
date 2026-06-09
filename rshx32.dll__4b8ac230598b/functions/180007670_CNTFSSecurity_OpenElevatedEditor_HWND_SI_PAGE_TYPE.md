# CNTFSSecurity::OpenElevatedEditor(HWND__ *,_SI_PAGE_TYPE)

- ea: `0x180007670`
- end: `0x180007777`
- name: `?OpenElevatedEditor@CNTFSSecurity@@UEAAJPEAUHWND__@@W4_SI_PAGE_TYPE@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(const OLECHAR **this, HWND, enum _SI_PAGE_TYPE)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006604`
- `0x180007670`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800076c0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800076d9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800076c0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800076d9`
- `OLEAUT32!__imp_SysFreeString` at `0x180007745`
- `OLEAUT32!__imp_SysFreeString` at `0x18000774e`
- `OLEAUT32!__imp_SysFreeString` at `0x180007745`
- `OLEAUT32!__imp_SysFreeString` at `0x18000774e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007758`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007758`
- `ole32!CoInitialize` at `0x18000769a`
- `ole32!CoInitialize` at `0x18000769a`

## pseudocode

```c
__int64 __fastcall CNTFSSecurity::OpenElevatedEditor(const OLECHAR **this, HWND a2, enum _SI_PAGE_TYPE a3)
{
  OLECHAR *v4; // rsi
  OLECHAR *v7; // rdi
  const struct _GUID *v8; // rdx
  HRESULT v9; // ebp
  const struct _GUID *v10; // r8
  HRESULT v11; // ebx
  BSTR v12; // rax
  void *v14; // [rsp+88h] [rbp+20h] BYREF

  v4 = 0;
  v14 = 0;
  v7 = 0;
  v9 = CoInitialize(0);
  if ( v9 < 0 )
  {
    v11 = v9;
  }
  else
  {
    v11 = CoCreateInstanceAsAdmin(a2, v8, v10, &v14);
    if ( v11 >= 0 )
    {
      v4 = SysAllocString(this[3]);
      if ( v4 && (v12 = SysAllocString(this[6]), (v7 = v12) != 0) )
        v11 = (*(__int64 (__fastcall **)(void *, HWND, OLECHAR *, BSTR, int, enum _SI_PAGE_TYPE))(*(_QWORD *)v14 + 24LL))(
                v14,
                a2,
                v4,
                v12,
                (*((_DWORD *)this + 8) >> 2) & 1,
                a3);
      else
        v11 = -2147024882;
    }
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  SysFreeString(v4);
  SysFreeString(v7);
  if ( v9 >= 0 )
    CoUninitialize();
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180007670  mov     rax, rsp
0x180007673  mov     [rax+8], rbx
0x180007677  mov     [rax+10h], rbp
0x18000767b  push    rsi
0x18000767c  push    rdi
0x18000767d  push    r12
0x18000767f  push    r14
0x180007681  push    r15
0x180007683  sub     rsp, 40h
0x180007687  mov     r14, rcx
0x18000768a  xor     esi, esi
0x18000768c  xor     ecx, ecx; pvReserved
0x18000768e  mov     [rax+20h], rsi
0x180007692  mov     r12d, r8d
0x180007695  mov     r15, rdx
0x180007698  xor     edi, edi
0x18000769a  call    cs:__imp_CoInitialize
0x1800076a0  mov     ebp, eax
0x1800076a2  test    eax, eax
0x1800076a4  js      short loc_18000771B
0x1800076a6  lea     r9, [rsp+68h+arg_18]; void **
0x1800076ae  mov     rcx, r15; HWND
0x1800076b1  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x1800076b6  mov     ebx, eax
0x1800076b8  test    eax, eax
0x1800076ba  js      short loc_18000771D
0x1800076bc  mov     rcx, [r14+18h]; psz
0x1800076c0  call    cs:__imp_SysAllocString
0x1800076c6  mov     rsi, rax
0x1800076c9  test    rax, rax
0x1800076cc  jnz     short loc_1800076D5
0x1800076ce  mov     ebx, 8007000Eh
0x1800076d3  jmp     short loc_18000771D
0x1800076d5  mov     rcx, [r14+30h]; psz
0x1800076d9  call    cs:__imp_SysAllocString
0x1800076df  mov     rdi, rax
0x1800076e2  test    rax, rax
0x1800076e5  jz      short loc_1800076CE
0x1800076e7  mov     edx, [r14+20h]
0x1800076eb  mov     r9, rdi
0x1800076ee  mov     rcx, [rsp+68h+arg_18]
0x1800076f6  mov     r8, rsi
0x1800076f9  shr     edx, 2
0x1800076fc  and     edx, 1
0x1800076ff  mov     [rsp+68h+var_40], r12d
0x180007704  mov     [rsp+68h+var_48], edx
0x180007708  mov     rdx, r15
0x18000770b  mov     rax, [rcx]
0x18000770e  mov     rax, [rax+18h]
0x180007712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007717  mov     ebx, eax
0x180007719  jmp     short loc_18000771D
0x18000771b  mov     ebx, ebp
0x18000771d  mov     rcx, [rsp+68h+arg_18]
0x180007725  test    rcx, rcx
0x180007728  jz      short loc_180007742
0x18000772a  mov     rax, [rcx]
0x18000772d  mov     rax, [rax+10h]
0x180007731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007736  mov     [rsp+68h+arg_18], 0
0x180007742  mov     rcx, rsi; bstrString
0x180007745  call    cs:__imp_SysFreeString
0x18000774b  mov     rcx, rdi; bstrString
0x18000774e  call    cs:__imp_SysFreeString
0x180007754  test    ebp, ebp
0x180007756  js      short loc_18000775E
0x180007758  call    cs:__imp_CoUninitialize
0x18000775e  mov     rbp, [rsp+68h+arg_8]
0x180007763  mov     eax, ebx
0x180007765  mov     rbx, [rsp+68h+arg_0]
0x18000776a  add     rsp, 40h
0x18000776e  pop     r15
0x180007770  pop     r14
0x180007772  pop     r12
0x180007774  pop     rdi
0x180007775  pop     rsi
0x180007776  retn
```
