# TaskServiceImpl::StoreMaintenanceLaunchPolicy(TaskServiceImpl::_MAINTENANCE_POLICY *,ushort *)

- ea: `0x18003d728`
- end: `0x18003d97f`
- name: `?StoreMaintenanceLaunchPolicy@TaskServiceImpl@@AEAAJPEAU_MAINTENANCE_POLICY@1@PEAG@Z`
- size: `599`
- prototype: `__int64 __fastcall(TaskServiceImpl *__hidden this, struct TaskServiceImpl::_MAINTENANCE_POLICY *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800493b0`

## callees

- `0x180026120`
- `0x18003d728`
- `0x18004a1f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003d7e1`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003d89d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003d92a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003d7e1`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003d89d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003d92a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003d7a9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003d86d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003d915`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003d7a9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003d86d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003d915`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d95c`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d95c`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18003d776`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18003d841`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18003d776`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18003d841`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TaskServiceImpl::StoreMaintenanceLaunchPolicy(
        TaskServiceImpl *this,
        struct TaskServiceImpl::_MAINTENANCE_POLICY *a2,
        unsigned __int16 *a3)
{
  BSTR lpData; // rbx
  DWORD cbData; // eax
  LSTATUS v6; // eax
  signed int v7; // edi
  LSTATUS v8; // eax
  int v9; // edx
  unsigned __int64 v10; // rcx
  signed int v11; // r8d
  OLECHAR *v12; // rcx
  DWORD v13; // eax
  signed int v14; // eax
  bool v15; // cc
  LSTATUS v16; // eax
  int v17; // edx
  unsigned __int64 v18; // rcx
  signed int v19; // r8d
  bool v20; // cc
  LSTATUS v21; // eax
  int v22; // edx
  unsigned __int64 v23; // rcx
  BSTR bstr; // [rsp+50h] [rbp+8h] BYREF
  BOOL Data; // [rsp+60h] [rbp+18h] BYREF
  int v27; // [rsp+64h] [rbp+1Ch]

  v27 = HIDWORD(a3);
  lpData = 0;
  bstr = 0;
  Data = 0;
  if ( *(_WORD *)a2 == 8 && *((_QWORD *)a2 + 1) )
  {
    ATL::CComBSTR::operator=(&bstr);
    lpData = bstr;
    cbData = SysStringByteLen(bstr);
    v6 = RegSetKeyValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
           L"Activation Boundary",
           1u,
           lpData,
           cbData);
    v7 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
      {
        v7 = (unsigned __int16)v6;
LABEL_29:
        v7 |= 0x80070000;
        goto LABEL_39;
      }
      goto LABEL_39;
    }
LABEL_15:
    if ( *((_WORD *)a2 + 12) == 8 && *((_QWORD *)a2 + 4) )
    {
      ATL::CComBSTR::operator=(&bstr);
      lpData = bstr;
      v13 = SysStringByteLen(bstr);
      v14 = RegSetKeyValueW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
              L"Random Delay",
              1u,
              lpData,
              v13);
      v15 = v14 <= 0;
      if ( v14 )
      {
LABEL_18:
        if ( !v15 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        v7 = v14;
        goto LABEL_39;
      }
    }
    else
    {
      v16 = RegDeleteKeyValueW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
              L"Random Delay");
      if ( v16 > 0 )
        v18 = (unsigned __int16)v16 | 0x80070000;
      else
        v18 = (unsigned int)v16;
      v7 = 0;
      if ( !tsched::IsErrorNotFound((tsched *)v18, v17) )
        v7 = v19;
      v20 = v7 <= 0;
      if ( v7 )
        goto LABEL_27;
    }
    if ( *((_WORD *)a2 + 24) == 11 )
    {
      Data = *((_WORD *)a2 + 28) == 0xFFFF;
      v14 = RegSetKeyValueW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
              L"WakeUp",
              4u,
              &Data,
              4u);
      v15 = v14 <= 0;
      if ( v14 )
        goto LABEL_18;
LABEL_38:
      v7 = 0;
      goto LABEL_39;
    }
    v21 = RegDeleteKeyValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
            L"WakeUp");
    v7 = v21;
    if ( v21 > 0 )
      v23 = (unsigned __int16)v21 | 0x80070000;
    else
      v23 = (unsigned int)v21;
    if ( tsched::IsErrorNotFound((tsched *)v23, v22) )
      goto LABEL_38;
    v20 = v7 <= 0;
    if ( !v7 )
      goto LABEL_38;
LABEL_27:
    if ( !v20 )
    {
      v7 = (unsigned __int16)v7;
      goto LABEL_29;
    }
LABEL_39:
    v12 = lpData;
    goto LABEL_40;
  }
  v8 = RegDeleteKeyValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
         L"Activation Boundary");
  if ( v8 > 0 )
    v10 = (unsigned __int16)v8 | 0x80070000;
  else
    v10 = (unsigned int)v8;
  v7 = 0;
  if ( !tsched::IsErrorNotFound((tsched *)v10, v9) )
    v7 = v11;
  if ( !v7 )
    goto LABEL_15;
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
  v12 = 0;
LABEL_40:
  SysFreeString(v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003d728  mov     rax, rsp
0x18003d72b  mov     [rax+10h], rbx
0x18003d72f  mov     [rax+20h], rsi
0x18003d733  mov     [rax+18h], r8
0x18003d737  mov     [rax+8], rcx
0x18003d73b  push    rdi
0x18003d73c  push    r14
0x18003d73e  push    r15
0x18003d740  sub     rsp, 30h
0x18003d744  mov     rsi, rdx
0x18003d747  xor     ebx, ebx
0x18003d749  mov     [rax+8], rbx
0x18003d74d  mov     [rax+18h], ebx
0x18003d750  mov     r15d, 80070000h
0x18003d756  cmp     word ptr [rdx], 8
0x18003d75a  jnz     short loc_18003D7C9
0x18003d75c  mov     rdx, [rdx+8]
0x18003d760  test    rdx, rdx
0x18003d763  jz      short loc_18003D7C9
0x18003d765  lea     rcx, [rax+8]
0x18003d769  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18003d76e  mov     rbx, [rsp+48h+bstr]
0x18003d773  mov     rcx, rbx; bstr
0x18003d776  call    cs:__imp_SysStringByteLen
0x18003d77d  nop     dword ptr [rax+rax+00h]
0x18003d782  mov     [rsp+48h+cbData], eax; cbData
0x18003d786  mov     [rsp+48h+lpData], rbx; lpData
0x18003d78b  mov     r9d, 1; dwType
0x18003d791  lea     r8, ValueName; "Activation Boundary"
0x18003d798  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003d79f  mov     r14, 0FFFFFFFF80000002h
0x18003d7a6  mov     rcx, r14; hKey
0x18003d7a9  call    cs:__imp_RegSetKeyValueW
0x18003d7b0  nop     dword ptr [rax+rax+00h]
0x18003d7b5  mov     edi, eax
0x18003d7b7  test    eax, eax
0x18003d7b9  jz      short loc_18003D81F
0x18003d7bb  jle     loc_18003D959
0x18003d7c1  movzx   edi, ax
0x18003d7c4  jmp     loc_18003D8D5
0x18003d7c9  lea     r8, ValueName; "Activation Boundary"
0x18003d7d0  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003d7d7  mov     r14, 0FFFFFFFF80000002h
0x18003d7de  mov     rcx, r14; hKey
0x18003d7e1  call    cs:__imp_RegDeleteKeyValueW
0x18003d7e8  nop     dword ptr [rax+rax+00h]
0x18003d7ed  mov     r8d, eax
0x18003d7f0  test    eax, eax
0x18003d7f2  jg      short loc_18003D7F8
0x18003d7f4  mov     ecx, eax
0x18003d7f6  jmp     short loc_18003D7FF
0x18003d7f8  movzx   ecx, r8w
0x18003d7fc  or      ecx, r15d; this
0x18003d7ff  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18003d804  xor     edi, edi
0x18003d806  test    al, al
0x18003d808  cmovz   edi, r8d
0x18003d80c  test    edi, edi
0x18003d80e  jz      short loc_18003D81F
0x18003d810  jle     short loc_18003D818
0x18003d812  movzx   edi, di
0x18003d815  or      edi, r15d
0x18003d818  xor     ecx, ecx
0x18003d81a  jmp     loc_18003D95C
0x18003d81f  cmp     word ptr [rsi+18h], 8
0x18003d824  jnz     short loc_18003D88C
0x18003d826  mov     rdx, [rsi+20h]
0x18003d82a  test    rdx, rdx
0x18003d82d  jz      short loc_18003D88C
0x18003d82f  lea     rcx, [rsp+48h+bstr]
0x18003d834  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18003d839  mov     rbx, [rsp+48h+bstr]
0x18003d83e  mov     rcx, rbx; bstr
0x18003d841  call    cs:__imp_SysStringByteLen
0x18003d848  nop     dword ptr [rax+rax+00h]
0x18003d84d  mov     [rsp+48h+cbData], eax; cbData
0x18003d851  mov     [rsp+48h+lpData], rbx; lpData
0x18003d856  mov     r9d, 1; dwType
0x18003d85c  lea     r8, aRandomDelay; "Random Delay"
0x18003d863  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003d86a  mov     rcx, r14; hKey
0x18003d86d  call    cs:__imp_RegSetKeyValueW
0x18003d874  nop     dword ptr [rax+rax+00h]
0x18003d879  test    eax, eax
0x18003d87b  jz      short loc_18003D8DA
0x18003d87d  jle     short loc_18003D885
0x18003d87f  movzx   eax, ax
0x18003d882  or      eax, r15d
0x18003d885  mov     edi, eax
0x18003d887  jmp     loc_18003D959
0x18003d88c  lea     r8, aRandomDelay; "Random Delay"
0x18003d893  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003d89a  mov     rcx, r14; hKey
0x18003d89d  call    cs:__imp_RegDeleteKeyValueW
0x18003d8a4  nop     dword ptr [rax+rax+00h]
0x18003d8a9  mov     r8d, eax
0x18003d8ac  test    eax, eax
0x18003d8ae  jg      short loc_18003D8B4
0x18003d8b0  mov     ecx, eax
0x18003d8b2  jmp     short loc_18003D8BB
0x18003d8b4  movzx   ecx, r8w
0x18003d8b8  or      ecx, r15d; this
0x18003d8bb  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18003d8c0  xor     edi, edi
0x18003d8c2  test    al, al
0x18003d8c4  cmovz   edi, r8d
0x18003d8c8  test    edi, edi
0x18003d8ca  jz      short loc_18003D8DA
0x18003d8cc  jle     loc_18003D959
0x18003d8d2  movzx   edi, di
0x18003d8d5  or      edi, r15d
0x18003d8d8  jmp     short loc_18003D959
0x18003d8da  lea     r8, aWakeup; "WakeUp"
0x18003d8e1  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003d8e8  mov     rcx, r14; hKey
0x18003d8eb  cmp     word ptr [rsi+30h], 0Bh
0x18003d8f0  jnz     short loc_18003D92A
0x18003d8f2  xor     eax, eax
0x18003d8f4  cmp     word ptr [rsi+38h], 0FFFFh
0x18003d8f9  setz    al
0x18003d8fc  mov     [rsp+48h+Data], eax
0x18003d900  mov     r9d, 4; dwType
0x18003d906  mov     [rsp+48h+cbData], r9d; cbData
0x18003d90b  lea     rax, [rsp+48h+Data]
0x18003d910  mov     [rsp+48h+lpData], rax; lpData
0x18003d915  call    cs:__imp_RegSetKeyValueW
0x18003d91c  nop     dword ptr [rax+rax+00h]
0x18003d921  test    eax, eax
0x18003d923  jz      short loc_18003D957
0x18003d925  jmp     loc_18003D87D
0x18003d92a  call    cs:__imp_RegDeleteKeyValueW
0x18003d931  nop     dword ptr [rax+rax+00h]
0x18003d936  mov     edi, eax
0x18003d938  test    eax, eax
0x18003d93a  jg      short loc_18003D940
0x18003d93c  mov     ecx, eax
0x18003d93e  jmp     short loc_18003D946
0x18003d940  movzx   ecx, di
0x18003d943  or      ecx, r15d; this
0x18003d946  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18003d94b  test    al, al
0x18003d94d  jnz     short loc_18003D957
0x18003d94f  test    edi, edi
0x18003d951  jnz     loc_18003D8CC
0x18003d957  xor     edi, edi
0x18003d959  mov     rcx, rbx; bstrString
0x18003d95c  call    cs:__imp_SysFreeString
0x18003d963  nop     dword ptr [rax+rax+00h]
0x18003d968  mov     eax, edi
0x18003d96a  mov     rbx, [rsp+48h+arg_8]
0x18003d96f  mov     rsi, [rsp+48h+arg_18]
0x18003d974  add     rsp, 30h
0x18003d978  pop     r15
0x18003d97a  pop     r14
0x18003d97c  pop     rdi
0x18003d97d  retn
```
