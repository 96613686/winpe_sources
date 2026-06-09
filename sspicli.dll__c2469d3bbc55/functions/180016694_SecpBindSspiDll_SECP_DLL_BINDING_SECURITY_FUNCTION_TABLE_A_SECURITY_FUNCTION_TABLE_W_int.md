# SecpBindSspiDll(_SECP_DLL_BINDING *,_SECURITY_FUNCTION_TABLE_A * *,_SECURITY_FUNCTION_TABLE_W * *,int *)

- ea: `0x180016694`
- end: `0x18001681c`
- name: `?SecpBindSspiDll@@YAJPEAU_SECP_DLL_BINDING@@PEAPEAU_SECURITY_FUNCTION_TABLE_A@@PEAPEAU_SECURITY_FUNCTION_TABLE_W@@PEAH@Z`
- size: `392`
- prototype: `__int64 __fastcall(struct _SECP_DLL_BINDING *, struct _SECURITY_FUNCTION_TABLE_A **, struct _SECURITY_FUNCTION_TABLE_W **, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e178`
- `0x18001c99c`

## callees

- `0x180016694`
- `0x180016824`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016800`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016800`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800166ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016705`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800166ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016705`

## string_xrefs

- `0x1800166e3`: `InitSecurityInterfaceW`
- `0x1800166fb`: `InitSecurityInterfaceA`

## pseudocode

```c
__int64 __fastcall SecpBindSspiDll(
        struct _SECP_DLL_BINDING *a1,
        struct _SECURITY_FUNCTION_TABLE_A **a2,
        struct _SECURITY_FUNCTION_TABLE_W **a3,
        int *a4)
{
  HMODULE v6; // rdi
  int v7; // ebx
  PSecurityFunctionTableW (__stdcall *ProcAddress)(); // r14
  PSecurityFunctionTableA (__stdcall *v9)(); // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  PSecurityFunctionTableA (__stdcall *v14)(); // rsi
  struct _SECURITY_FUNCTION_TABLE_A *v15; // rbx
  struct _SECURITY_FUNCTION_TABLE_W *v16; // rcx

  v6 = 0;
  v7 = SecpResolveBindingPath(a1);
  if ( v7 < 0 )
  {
LABEL_20:
    if ( v7 >= 0 )
      return (unsigned int)v7;
    goto LABEL_21;
  }
  v6 = (HMODULE)*((_QWORD *)a1 + 1);
  if ( !v6 )
    goto LABEL_3;
  *a4 = 0;
  ProcAddress = (PSecurityFunctionTableW (__stdcall *)())GetProcAddress(v6, "InitSecurityInterfaceW");
  v9 = (PSecurityFunctionTableA (__stdcall *)())GetProcAddress(v6, "InitSecurityInterfaceA");
  v14 = v9;
  if ( !ProcAddress && !v9 )
    goto LABEL_3;
  if ( ProcAddress == InitSecurityInterfaceW || v9 == InitSecurityInterfaceA )
  {
    v7 = -2146893051;
    goto LABEL_20;
  }
  if ( v9 )
    v15 = v9();
  else
    v15 = 0;
  if ( ProcAddress )
    v16 = (struct _SECURITY_FUNCTION_TABLE_W *)((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))ProcAddress)(
                                                 v11,
                                                 v10,
                                                 v12,
                                                 v13);
  else
    v16 = 0;
  if ( (!ProcAddress || v16) && (!v14 || v15) )
  {
    *a3 = v16;
    *a2 = v15;
    v7 = 0;
    goto LABEL_20;
  }
LABEL_3:
  v7 = -2146893051;
LABEL_21:
  if ( v6 )
  {
    FreeLibrary(v6);
    *((_QWORD *)a1 + 1) = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180016694  mov     [rsp+arg_10], r8
0x180016699  mov     [rsp+arg_8], rdx
0x18001669e  mov     [rsp+arg_0], rcx
0x1800166a3  push    rbx
0x1800166a4  push    rsi
0x1800166a5  push    rdi
0x1800166a6  push    r14
0x1800166a8  push    r15
0x1800166aa  sub     rsp, 50h
0x1800166ae  mov     rsi, r9
0x1800166b1  mov     r15, rcx
0x1800166b4  xor     edi, edi
0x1800166b6  call    ?SecpResolveBindingPath@@YAJPEAU_SECP_DLL_BINDING@@@Z; SecpResolveBindingPath(_SECP_DLL_BINDING *)
0x1800166bb  mov     ebx, eax
0x1800166bd  test    eax, eax
0x1800166bf  js      loc_1800167F4
0x1800166c5  mov     rdi, [r15+8]
0x1800166c9  mov     [rsp+78h+var_50], rdi
0x1800166ce  test    rdi, rdi
0x1800166d1  jnz     short loc_1800166DD
0x1800166d3  mov     ebx, 80090305h
0x1800166d8  jmp     loc_1800167F8
0x1800166dd  mov     dword ptr [rsi], 0
0x1800166e3  lea     rdx, aInitsecurityin_2; "InitSecurityInterfaceW"
0x1800166ea  mov     rcx, rdi; hModule
0x1800166ed  call    cs:__imp_GetProcAddress
0x1800166f3  mov     r14, rax
0x1800166f6  mov     [rsp+78h+var_48], rax
0x1800166fb  lea     rdx, aInitsecurityin_1; "InitSecurityInterfaceA"
0x180016702  mov     rcx, rdi; hModule
0x180016705  call    cs:__imp_GetProcAddress
0x18001670b  mov     rsi, rax
0x18001670e  mov     [rsp+78h+var_40], rax
0x180016713  test    r14, r14
0x180016716  jnz     short loc_18001671D
0x180016718  test    rax, rax
0x18001671b  jz      short loc_1800166D3
0x18001671d  lea     rax, InitSecurityInterfaceW
0x180016724  cmp     r14, rax
0x180016727  jz      loc_1800167EF
0x18001672d  lea     rax, InitSecurityInterfaceA
0x180016734  cmp     rsi, rax
0x180016737  jz      loc_1800167EF
0x18001673d  test    rsi, rsi
0x180016740  jz      short loc_180016774
0x180016742  mov     rax, rsi
0x180016745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001674a  mov     rbx, rax
0x18001674d  mov     [rsp+78h+var_58], rax
0x180016752  jmp     short loc_18001677B
0x180016754  xor     ebx, ebx
0x180016756  mov     [rsp+78h+var_58], rbx
0x18001675b  mov     r15, [rsp+78h+arg_0]
0x180016763  mov     rdi, [rsp+78h+var_50]
0x180016768  mov     r14, [rsp+78h+var_48]
0x18001676d  mov     rsi, [rsp+78h+var_40]
0x180016772  jmp     short loc_18001677B
0x180016774  xor     ebx, ebx
0x180016776  mov     [rsp+78h+var_58], rbx
0x18001677b  test    r14, r14
0x18001677e  jz      short loc_1800167B7
0x180016780  mov     rax, r14
0x180016783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016788  mov     rcx, rax
0x18001678b  mov     [rsp+78h+var_38], rax
0x180016790  jmp     short loc_1800167B9
0x180016792  xor     ecx, ecx
0x180016794  mov     [rsp+78h+var_38], rcx
0x180016799  mov     r15, [rsp+78h+arg_0]
0x1800167a1  mov     rdi, [rsp+78h+var_50]
0x1800167a6  mov     r14, [rsp+78h+var_48]
0x1800167ab  mov     rsi, [rsp+78h+var_40]
0x1800167b0  mov     rbx, [rsp+78h+var_58]
0x1800167b5  jmp     short loc_1800167B9
0x1800167b7  xor     ecx, ecx
0x1800167b9  test    r14, r14
0x1800167bc  jz      short loc_1800167C7
0x1800167be  test    rcx, rcx
0x1800167c1  jz      loc_1800166D3
0x1800167c7  test    rsi, rsi
0x1800167ca  jz      short loc_1800167D5
0x1800167cc  test    rbx, rbx
0x1800167cf  jz      loc_1800166D3
0x1800167d5  mov     rax, [rsp+78h+arg_10]
0x1800167dd  mov     [rax], rcx
0x1800167e0  mov     rax, [rsp+78h+arg_8]
0x1800167e8  mov     [rax], rbx
0x1800167eb  xor     ebx, ebx
0x1800167ed  jmp     short loc_1800167F4
0x1800167ef  mov     ebx, 80090305h
0x1800167f4  test    ebx, ebx
0x1800167f6  jns     short loc_18001680E
0x1800167f8  test    rdi, rdi
0x1800167fb  jz      short loc_18001680E
0x1800167fd  mov     rcx, rdi; hLibModule
0x180016800  call    cs:__imp_FreeLibrary
0x180016806  mov     qword ptr [r15+8], 0
0x18001680e  mov     eax, ebx
0x180016810  add     rsp, 50h
0x180016814  pop     r15
0x180016816  pop     r14
0x180016818  pop     rdi
0x180016819  pop     rsi
0x18001681a  pop     rbx
0x18001681b  retn
```
