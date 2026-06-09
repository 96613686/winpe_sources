# CUPnPAutomationProxy::FreeControlResponse(tagUPNP_CONTROL_RESPONSE *)

- ea: `0x18003817c`
- end: `0x180038275`
- name: `?FreeControlResponse@CUPnPAutomationProxy@@AEAAXPEAUtagUPNP_CONTROL_RESPONSE@@@Z`
- size: `249`
- prototype: `void __fastcall(CUPnPAutomationProxy *__hidden this, struct tagUPNP_CONTROL_RESPONSE *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f590`
- `0x1800537b4`

## callees

- `0x18003817c`
- `0x180053e18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800381d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800381d8`
- `OLEAUT32!__imp_SysFreeString` at `0x180038191`
- `OLEAUT32!__imp_SysFreeString` at `0x1800381fe`
- `OLEAUT32!__imp_SysFreeString` at `0x18003821b`
- `OLEAUT32!__imp_SysFreeString` at `0x180038238`
- `OLEAUT32!__imp_SysFreeString` at `0x180038255`
- `OLEAUT32!__imp_SysFreeString` at `0x180038191`
- `OLEAUT32!__imp_SysFreeString` at `0x1800381fe`
- `OLEAUT32!__imp_SysFreeString` at `0x18003821b`
- `OLEAUT32!__imp_SysFreeString` at `0x180038238`
- `OLEAUT32!__imp_SysFreeString` at `0x180038255`

## pseudocode

```c
void __fastcall CUPnPAutomationProxy::FreeControlResponse(
        CUPnPAutomationProxy *this,
        struct tagUPNP_CONTROL_RESPONSE *a2)
{
  __int64 i; // rdi
  OLECHAR *v4; // rcx
  OLECHAR *v5; // rcx
  OLECHAR *v6; // rcx
  OLECHAR *v7; // rcx

  if ( *(_QWORD *)a2 )
  {
    SysFreeString(*(BSTR *)a2);
    *(_QWORD *)a2 = 0;
  }
  if ( *((_DWORD *)a2 + 2) )
  {
    if ( *((_QWORD *)a2 + 3) )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)a2 + 4); i = (unsigned int)(i + 1) )
        SafeClearVariant((VARIANT *)(*((_QWORD *)a2 + 3) + 24 * i));
      CoTaskMemFree(*((LPVOID *)a2 + 3));
      *((_QWORD *)a2 + 3) = 0;
      *((_DWORD *)a2 + 4) = 0;
    }
  }
  else
  {
    v4 = (OLECHAR *)*((_QWORD *)a2 + 2);
    if ( v4 )
    {
      SysFreeString(v4);
      *((_QWORD *)a2 + 2) = 0;
    }
    v5 = (OLECHAR *)*((_QWORD *)a2 + 3);
    if ( v5 )
    {
      SysFreeString(v5);
      *((_QWORD *)a2 + 3) = 0;
    }
    v6 = (OLECHAR *)*((_QWORD *)a2 + 4);
    if ( v6 )
    {
      SysFreeString(v6);
      *((_QWORD *)a2 + 4) = 0;
    }
    v7 = (OLECHAR *)*((_QWORD *)a2 + 5);
    if ( v7 )
    {
      SysFreeString(v7);
      *((_QWORD *)a2 + 5) = 0;
    }
  }
}

```

## disassembly

```asm
0x18003817c  mov     [rsp+arg_0], rbx
0x180038181  push    rdi
0x180038182  sub     rsp, 20h
0x180038186  mov     rcx, [rdx]; bstrString
0x180038189  mov     rbx, rdx
0x18003818c  test    rcx, rcx
0x18003818f  jz      short loc_1800381A4
0x180038191  call    cs:__imp_SysFreeString
0x180038198  nop     dword ptr [rax+rax+00h]
0x18003819d  mov     qword ptr [rbx], 0
0x1800381a4  cmp     dword ptr [rbx+8], 0
0x1800381a8  jz      short loc_1800381F5
0x1800381aa  cmp     qword ptr [rbx+18h], 0
0x1800381af  jz      loc_180038269
0x1800381b5  xor     edi, edi
0x1800381b7  cmp     [rbx+10h], edi
0x1800381ba  jbe     short loc_1800381D4
0x1800381bc  mov     rax, [rbx+18h]
0x1800381c0  lea     rcx, [rdi+rdi*2]
0x1800381c4  lea     rcx, [rax+rcx*8]; VARIANT *
0x1800381c8  call    ?SafeClearVariant@@YAXPEAUtagVARIANT@@@Z; SafeClearVariant(tagVARIANT *)
0x1800381cd  inc     edi
0x1800381cf  cmp     edi, [rbx+10h]
0x1800381d2  jb      short loc_1800381BC
0x1800381d4  mov     rcx, [rbx+18h]; pv
0x1800381d8  call    cs:__imp_CoTaskMemFree
0x1800381df  nop     dword ptr [rax+rax+00h]
0x1800381e4  mov     qword ptr [rbx+18h], 0
0x1800381ec  mov     dword ptr [rbx+10h], 0
0x1800381f3  jmp     short loc_180038269
0x1800381f5  mov     rcx, [rbx+10h]; bstrString
0x1800381f9  test    rcx, rcx
0x1800381fc  jz      short loc_180038212
0x1800381fe  call    cs:__imp_SysFreeString
0x180038205  nop     dword ptr [rax+rax+00h]
0x18003820a  mov     qword ptr [rbx+10h], 0
0x180038212  mov     rcx, [rbx+18h]; bstrString
0x180038216  test    rcx, rcx
0x180038219  jz      short loc_18003822F
0x18003821b  call    cs:__imp_SysFreeString
0x180038222  nop     dword ptr [rax+rax+00h]
0x180038227  mov     qword ptr [rbx+18h], 0
0x18003822f  mov     rcx, [rbx+20h]; bstrString
0x180038233  test    rcx, rcx
0x180038236  jz      short loc_18003824C
0x180038238  call    cs:__imp_SysFreeString
0x18003823f  nop     dword ptr [rax+rax+00h]
0x180038244  mov     qword ptr [rbx+20h], 0
0x18003824c  mov     rcx, [rbx+28h]; bstrString
0x180038250  test    rcx, rcx
0x180038253  jz      short loc_180038269
0x180038255  call    cs:__imp_SysFreeString
0x18003825c  nop     dword ptr [rax+rax+00h]
0x180038261  mov     qword ptr [rbx+28h], 0
0x180038269  mov     rbx, [rsp+28h+arg_0]
0x18003826e  add     rsp, 20h
0x180038272  pop     rdi
0x180038273  retn
```
