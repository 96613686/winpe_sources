# SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)

- ea: `0x18000b300`
- end: `0x18000b492`
- name: `?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(OLECHAR *psz, struct IXMLDOMDocument2 **)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004c48`
- `0x1800050c0`
- `0x180005260`
- `0x180005404`
- `0x1800062c4`

## callees

- `0x18000b13c`
- `0x18000b300`
- `0x18000d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000b3c8`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b3c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b470`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b470`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b37e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b37e`

## string_xrefs

- `0x18000b33d`: `SdpXmlCreate`

## pseudocode

```c
__int64 __fastcall SdpXmlCreate(OLECHAR *psz, LPVOID *a2)
{
  OLECHAR *v4; // rdi
  int v5; // r8d
  int v6; // r9d
  unsigned int v7; // ebx
  HRESULT v8; // eax
  int v9; // eax
  BSTR v10; // rax
  int v11; // eax
  LPVOID v12; // rcx
  __int16 v14; // [rsp+50h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+18h] BYREF

  v14 = -1;
  ppv = 0;
  v4 = 0;
  if ( !psz )
  {
    v5 = 462;
LABEL_3:
    v6 = -2147024809;
    v7 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"SdpXmlCreate", v5, v6);
    goto LABEL_18;
  }
  if ( !a2 )
  {
    v5 = 463;
    goto LABEL_3;
  }
  v8 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x15u, &IID_IXMLDOMDocument2, &ppv);
  v7 = v8;
  if ( v8 < 0 )
  {
    v6 = v8;
    v5 = 470;
    goto LABEL_4;
  }
  v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  v7 = v9;
  if ( v9 < 0 )
  {
    v6 = v9;
    v5 = 473;
    goto LABEL_4;
  }
  v10 = SysAllocString(psz);
  v4 = v10;
  if ( !v10 )
  {
    v7 = -2147024882;
    v5 = 476;
    v6 = -2147024882;
    goto LABEL_4;
  }
  v11 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, v10, &v14);
  v7 = v11;
  if ( v11 < 0 )
  {
    v6 = v11;
    v5 = 479;
    goto LABEL_4;
  }
  if ( !v14 )
  {
    v7 = -2147467259;
    v5 = 480;
    v6 = -2147467259;
    goto LABEL_4;
  }
  v12 = ppv;
  *a2 = ppv;
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 8LL))(v12);
LABEL_18:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v4 )
    SysFreeString(v4);
  return v7;
}

```

## disassembly

```asm
0x18000b300  mov     [rsp+arg_8], rbx
0x18000b305  mov     [rsp+arg_18], rbp
0x18000b30a  push    rsi
0x18000b30b  push    rdi
0x18000b30c  push    r14
0x18000b30e  sub     rsp, 30h
0x18000b312  xor     ebp, ebp
0x18000b314  or      eax, 0FFFFFFFFh
0x18000b317  mov     [rsp+48h+arg_0], ax
0x18000b31c  mov     r14, rdx
0x18000b31f  mov     [rsp+48h+arg_10], rbp
0x18000b324  mov     rsi, rcx
0x18000b327  mov     edi, ebp
0x18000b329  test    rcx, rcx
0x18000b32c  jnz     short loc_18000B353
0x18000b32e  mov     r8d, 1CEh; int
0x18000b334  mov     r9d, 80070057h; int
0x18000b33a  mov     ebx, r9d
0x18000b33d  lea     rdx, aSdpxmlcreate; "SdpXmlCreate"
0x18000b344  mov     ecx, 1; Level
0x18000b349  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000b34e  jmp     loc_18000B44D
0x18000b353  test    r14, r14
0x18000b356  jnz     short loc_18000B360
0x18000b358  mov     r8d, 1CFh
0x18000b35e  jmp     short loc_18000B334
0x18000b360  xor     edx, edx; pUnkOuter
0x18000b362  lea     rax, [rsp+48h+arg_10]
0x18000b367  lea     r9, IID_IXMLDOMDocument2; riid
0x18000b36e  mov     [rsp+48h+ppv], rax; ppv
0x18000b373  lea     rcx, CLSID_DOMDocument60; rclsid
0x18000b37a  lea     r8d, [rdx+15h]; dwClsContext
0x18000b37e  call    cs:__imp_CoCreateInstance
0x18000b385  nop     dword ptr [rax+rax+00h]
0x18000b38a  mov     ebx, eax
0x18000b38c  test    eax, eax
0x18000b38e  jns     short loc_18000B39B
0x18000b390  mov     r9d, eax
0x18000b393  mov     r8d, 1D6h
0x18000b399  jmp     short loc_18000B33D
0x18000b39b  mov     rcx, [rsp+48h+arg_10]
0x18000b3a0  xor     edx, edx
0x18000b3a2  mov     rax, [rcx]
0x18000b3a5  mov     rax, [rax+1F8h]
0x18000b3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3b1  mov     ebx, eax
0x18000b3b3  test    eax, eax
0x18000b3b5  jns     short loc_18000B3C5
0x18000b3b7  mov     r9d, eax
0x18000b3ba  mov     r8d, 1D9h
0x18000b3c0  jmp     loc_18000B33D
0x18000b3c5  mov     rcx, rsi; psz
0x18000b3c8  call    cs:__imp_SysAllocString
0x18000b3cf  nop     dword ptr [rax+rax+00h]
0x18000b3d4  mov     rdi, rax
0x18000b3d7  test    rax, rax
0x18000b3da  jnz     short loc_18000B3EF
0x18000b3dc  mov     ebx, 8007000Eh
0x18000b3e1  mov     r8d, 1DCh
0x18000b3e7  mov     r9d, ebx
0x18000b3ea  jmp     loc_18000B33D
0x18000b3ef  mov     rcx, [rsp+48h+arg_10]
0x18000b3f4  lea     r8, [rsp+48h+arg_0]
0x18000b3f9  mov     rdx, rdi
0x18000b3fc  mov     rax, [rcx]
0x18000b3ff  mov     rax, [rax+208h]
0x18000b406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b40b  mov     ebx, eax
0x18000b40d  test    eax, eax
0x18000b40f  jns     short loc_18000B41F
0x18000b411  mov     r9d, eax
0x18000b414  mov     r8d, 1DFh
0x18000b41a  jmp     loc_18000B33D
0x18000b41f  cmp     [rsp+48h+arg_0], bp
0x18000b424  jnz     short loc_18000B439
0x18000b426  mov     ebx, 80004005h
0x18000b42b  mov     r8d, 1E0h
0x18000b431  mov     r9d, ebx
0x18000b434  jmp     loc_18000B33D
0x18000b439  mov     rcx, [rsp+48h+arg_10]
0x18000b43e  mov     [r14], rcx
0x18000b441  mov     rax, [rcx]
0x18000b444  mov     rax, [rax+8]
0x18000b448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b44d  mov     rcx, [rsp+48h+arg_10]
0x18000b452  test    rcx, rcx
0x18000b455  jz      short loc_18000B468
0x18000b457  mov     rax, [rcx]
0x18000b45a  mov     rax, [rax+10h]
0x18000b45e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b463  mov     [rsp+48h+arg_10], rbp
0x18000b468  test    rdi, rdi
0x18000b46b  jz      short loc_18000B47C
0x18000b46d  mov     rcx, rdi; bstrString
0x18000b470  call    cs:__imp_SysFreeString
0x18000b477  nop     dword ptr [rax+rax+00h]
0x18000b47c  mov     rbp, [rsp+48h+arg_18]
0x18000b481  mov     eax, ebx
0x18000b483  mov     rbx, [rsp+48h+arg_8]
0x18000b488  add     rsp, 30h
0x18000b48c  pop     r14
0x18000b48e  pop     rdi
0x18000b48f  pop     rsi
0x18000b490  retn
```
