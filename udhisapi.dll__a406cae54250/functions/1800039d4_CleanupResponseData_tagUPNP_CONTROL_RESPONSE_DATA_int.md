# CleanupResponseData(tagUPNP_CONTROL_RESPONSE_DATA *,int)

- ea: `0x1800039d4`
- end: `0x180003a8d`
- name: `?CleanupResponseData@@YAXPEATtagUPNP_CONTROL_RESPONSE_DATA@@H@Z`
- size: `185`
- prototype: `void __fastcall(union tagUPNP_CONTROL_RESPONSE_DATA *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000512c`
- `0x1800063e0`

## callees

- `0x1800039d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a12`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a30`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a46`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a5d`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a74`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a30`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a46`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a5d`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a74`
- `OLEAUT32!__imp_VariantClear` at `0x180003a02`
- `OLEAUT32!__imp_VariantClear` at `0x180003a02`

## pseudocode

```c
void __fastcall CleanupResponseData(union tagUPNP_CONTROL_RESPONSE_DATA *a1, int a2)
{
  __int64 i; // rdi
  OLECHAR *v4; // rcx
  OLECHAR *v5; // rcx
  OLECHAR *v6; // rcx
  OLECHAR *v7; // rcx

  if ( a2 )
  {
    if ( *((_QWORD *)a1 + 1) )
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)a1; i = (unsigned int)(i + 1) )
        VariantClear((VARIANTARG *)(*((_QWORD *)a1 + 1) + 24 * i));
      CoTaskMemFree(*((LPVOID *)a1 + 1));
      *((_QWORD *)a1 + 1) = 0;
      *(_DWORD *)a1 = 0;
    }
  }
  else
  {
    v4 = *(OLECHAR **)a1;
    if ( v4 )
    {
      SysFreeString(v4);
      *(_QWORD *)a1 = 0;
    }
    v5 = (OLECHAR *)*((_QWORD *)a1 + 1);
    if ( v5 )
    {
      SysFreeString(v5);
      *((_QWORD *)a1 + 1) = 0;
    }
    v6 = (OLECHAR *)*((_QWORD *)a1 + 2);
    if ( v6 )
    {
      SysFreeString(v6);
      *((_QWORD *)a1 + 2) = 0;
    }
    v7 = (OLECHAR *)*((_QWORD *)a1 + 3);
    if ( v7 )
    {
      SysFreeString(v7);
      *((_QWORD *)a1 + 3) = 0;
    }
  }
}

```

## disassembly

```asm
0x1800039d4  mov     [rsp+arg_0], rbx
0x1800039d9  push    rdi
0x1800039da  sub     rsp, 20h
0x1800039de  mov     rbx, rcx
0x1800039e1  test    edx, edx
0x1800039e3  jz      short loc_180003A28
0x1800039e5  cmp     qword ptr [rcx+8], 0
0x1800039ea  jz      loc_180003A82
0x1800039f0  xor     edi, edi
0x1800039f2  cmp     [rcx], edi
0x1800039f4  jbe     short loc_180003A0E
0x1800039f6  mov     rax, [rbx+8]
0x1800039fa  lea     rcx, [rdi+rdi*2]
0x1800039fe  lea     rcx, [rax+rcx*8]; pvarg
0x180003a02  call    cs:__imp_VariantClear
0x180003a08  inc     edi
0x180003a0a  cmp     edi, [rbx]
0x180003a0c  jb      short loc_1800039F6
0x180003a0e  mov     rcx, [rbx+8]; pv
0x180003a12  call    cs:__imp_CoTaskMemFree
0x180003a18  mov     qword ptr [rbx+8], 0
0x180003a20  mov     dword ptr [rbx], 0
0x180003a26  jmp     short loc_180003A82
0x180003a28  mov     rcx, [rcx]; bstrString
0x180003a2b  test    rcx, rcx
0x180003a2e  jz      short loc_180003A3D
0x180003a30  call    cs:__imp_SysFreeString
0x180003a36  mov     qword ptr [rbx], 0
0x180003a3d  mov     rcx, [rbx+8]; bstrString
0x180003a41  test    rcx, rcx
0x180003a44  jz      short loc_180003A54
0x180003a46  call    cs:__imp_SysFreeString
0x180003a4c  mov     qword ptr [rbx+8], 0
0x180003a54  mov     rcx, [rbx+10h]; bstrString
0x180003a58  test    rcx, rcx
0x180003a5b  jz      short loc_180003A6B
0x180003a5d  call    cs:__imp_SysFreeString
0x180003a63  mov     qword ptr [rbx+10h], 0
0x180003a6b  mov     rcx, [rbx+18h]; bstrString
0x180003a6f  test    rcx, rcx
0x180003a72  jz      short loc_180003A82
0x180003a74  call    cs:__imp_SysFreeString
0x180003a7a  mov     qword ptr [rbx+18h], 0
0x180003a82  mov     rbx, [rsp+28h+arg_0]
0x180003a87  add     rsp, 20h
0x180003a8b  pop     rdi
0x180003a8c  retn
```
