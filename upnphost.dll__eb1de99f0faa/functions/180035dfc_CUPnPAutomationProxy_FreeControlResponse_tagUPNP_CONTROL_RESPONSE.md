# CUPnPAutomationProxy::FreeControlResponse(tagUPNP_CONTROL_RESPONSE *)

- ea: `0x180035dfc`
- end: `0x180035ed0`
- name: `?FreeControlResponse@CUPnPAutomationProxy@@AEAAXPEAUtagUPNP_CONTROL_RESPONSE@@@Z`
- size: `212`
- prototype: `void __fastcall(CUPnPAutomationProxy *__hidden this, struct tagUPNP_CONTROL_RESPONSE *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002dd70`
- `0x180050164`

## callees

- `0x180035dfc`
- `0x180050790`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035e52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035e52`
- `OLEAUT32!__imp_SysFreeString` at `0x180035e11`
- `OLEAUT32!__imp_SysFreeString` at `0x180035e72`
- `OLEAUT32!__imp_SysFreeString` at `0x180035e89`
- `OLEAUT32!__imp_SysFreeString` at `0x180035ea0`
- `OLEAUT32!__imp_SysFreeString` at `0x180035eb7`
- `OLEAUT32!__imp_SysFreeString` at `0x180035e11`
- `OLEAUT32!__imp_SysFreeString` at `0x180035e72`
- `OLEAUT32!__imp_SysFreeString` at `0x180035e89`
- `OLEAUT32!__imp_SysFreeString` at `0x180035ea0`
- `OLEAUT32!__imp_SysFreeString` at `0x180035eb7`

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
0x180035dfc  mov     [rsp+arg_0], rbx
0x180035e01  push    rdi
0x180035e02  sub     rsp, 20h
0x180035e06  mov     rcx, [rdx]; bstrString
0x180035e09  mov     rbx, rdx
0x180035e0c  test    rcx, rcx
0x180035e0f  jz      short loc_180035E1E
0x180035e11  call    cs:__imp_SysFreeString
0x180035e17  mov     qword ptr [rbx], 0
0x180035e1e  cmp     dword ptr [rbx+8], 0
0x180035e22  jz      short loc_180035E69
0x180035e24  cmp     qword ptr [rbx+18h], 0
0x180035e29  jz      loc_180035EC5
0x180035e2f  xor     edi, edi
0x180035e31  cmp     [rbx+10h], edi
0x180035e34  jbe     short loc_180035E4E
0x180035e36  mov     rax, [rbx+18h]
0x180035e3a  lea     rcx, [rdi+rdi*2]
0x180035e3e  lea     rcx, [rax+rcx*8]; VARIANT *
0x180035e42  call    ?SafeClearVariant@@YAXPEAUtagVARIANT@@@Z; SafeClearVariant(tagVARIANT *)
0x180035e47  inc     edi
0x180035e49  cmp     edi, [rbx+10h]
0x180035e4c  jb      short loc_180035E36
0x180035e4e  mov     rcx, [rbx+18h]; pv
0x180035e52  call    cs:__imp_CoTaskMemFree
0x180035e58  mov     qword ptr [rbx+18h], 0
0x180035e60  mov     dword ptr [rbx+10h], 0
0x180035e67  jmp     short loc_180035EC5
0x180035e69  mov     rcx, [rbx+10h]; bstrString
0x180035e6d  test    rcx, rcx
0x180035e70  jz      short loc_180035E80
0x180035e72  call    cs:__imp_SysFreeString
0x180035e78  mov     qword ptr [rbx+10h], 0
0x180035e80  mov     rcx, [rbx+18h]; bstrString
0x180035e84  test    rcx, rcx
0x180035e87  jz      short loc_180035E97
0x180035e89  call    cs:__imp_SysFreeString
0x180035e8f  mov     qword ptr [rbx+18h], 0
0x180035e97  mov     rcx, [rbx+20h]; bstrString
0x180035e9b  test    rcx, rcx
0x180035e9e  jz      short loc_180035EAE
0x180035ea0  call    cs:__imp_SysFreeString
0x180035ea6  mov     qword ptr [rbx+20h], 0
0x180035eae  mov     rcx, [rbx+28h]; bstrString
0x180035eb2  test    rcx, rcx
0x180035eb5  jz      short loc_180035EC5
0x180035eb7  call    cs:__imp_SysFreeString
0x180035ebd  mov     qword ptr [rbx+28h], 0
0x180035ec5  mov     rbx, [rsp+28h+arg_0]
0x180035eca  add     rsp, 20h
0x180035ece  pop     rdi
0x180035ecf  retn
```
