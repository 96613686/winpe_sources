# TaskServiceImpl::StoreMaintenanceLaunchPolicy(TaskServiceImpl::_MAINTENANCE_POLICY *,ushort *)

- ea: `0x18003a264`
- end: `0x18003a47c`
- name: `?StoreMaintenanceLaunchPolicy@TaskServiceImpl@@AEAAJPEAU_MAINTENANCE_POLICY@1@PEAG@Z`
- size: `536`
- prototype: `__int64 __fastcall(TaskServiceImpl *__hidden this, struct TaskServiceImpl::_MAINTENANCE_POLICY *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180045c30`

## callees

- `0x180024460`
- `0x18003a264`
- `0x180046918`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003a311`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003a3bb`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003a438`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003a311`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003a3bb`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003a438`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003a2df`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003a391`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003a429`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003a2df`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003a391`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003a429`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a460`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a460`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18003a2b2`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18003a36b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18003a2b2`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18003a36b`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall TaskServiceImpl::StoreMaintenanceLaunchPolicy(
        TaskServiceImpl *this,
        struct TaskServiceImpl::_MAINTENANCE_POLICY *a2,
        unsigned __int16 *a3)
{
  BSTR lpData; // rbx
  __int64 v5; // rdx
  DWORD cbData; // eax
  LSTATUS v7; // eax
  __int64 v8; // r8
  signed int v9; // edi
  LSTATUS v10; // eax
  int v11; // edx
  unsigned __int64 v12; // rcx
  OLECHAR *v13; // rcx
  __int64 v14; // rdx
  DWORD v15; // eax
  signed int v16; // eax
  bool v17; // cc
  LSTATUS v18; // eax
  int v19; // edx
  unsigned __int64 v20; // rcx
  signed int v21; // r8d
  bool v22; // cc
  LSTATUS v23; // eax
  int v24; // edx
  unsigned __int64 v25; // rcx
  BSTR bstr; // [rsp+50h] [rbp+8h] BYREF
  BOOL Data; // [rsp+60h] [rbp+18h] BYREF
  int v29; // [rsp+64h] [rbp+1Ch]

  v29 = HIDWORD(a3);
  lpData = 0;
  bstr = 0;
  Data = 0;
  if ( *(_WORD *)a2 == 8 )
  {
    v5 = *((_QWORD *)a2 + 1);
    if ( v5 )
    {
      ATL::CComBSTR::operator=(&bstr, v5, a3);
      lpData = bstr;
      cbData = SysStringByteLen(bstr);
      v7 = RegSetKeyValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
             L"Activation Boundary",
             1u,
             lpData,
             cbData);
      v9 = v7;
      if ( v7 )
      {
        if ( v7 > 0 )
        {
          v9 = (unsigned __int16)v7;
LABEL_29:
          v9 |= 0x80070000;
          goto LABEL_39;
        }
        goto LABEL_39;
      }
LABEL_15:
      if ( *((_WORD *)a2 + 12) == 8 && (v14 = *((_QWORD *)a2 + 4)) != 0 )
      {
        ATL::CComBSTR::operator=(&bstr, v14, v8);
        lpData = bstr;
        v15 = SysStringByteLen(bstr);
        v16 = RegSetKeyValueW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
                L"Random Delay",
                1u,
                lpData,
                v15);
        v17 = v16 <= 0;
        if ( v16 )
        {
LABEL_18:
          if ( !v17 )
            v16 = (unsigned __int16)v16 | 0x80070000;
          v9 = v16;
          goto LABEL_39;
        }
      }
      else
      {
        v18 = RegDeleteKeyValueW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
                L"Random Delay");
        if ( v18 > 0 )
          v20 = (unsigned __int16)v18 | 0x80070000;
        else
          v20 = (unsigned int)v18;
        v9 = 0;
        if ( !tsched::IsErrorNotFound((tsched *)v20, v19) )
          v9 = v21;
        v22 = v9 <= 0;
        if ( v9 )
          goto LABEL_27;
      }
      if ( *((_WORD *)a2 + 24) == 11 )
      {
        Data = *((_WORD *)a2 + 28) == 0xFFFF;
        v16 = RegSetKeyValueW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
                L"WakeUp",
                4u,
                &Data,
                4u);
        v17 = v16 <= 0;
        if ( v16 )
          goto LABEL_18;
LABEL_38:
        v9 = 0;
        goto LABEL_39;
      }
      v23 = RegDeleteKeyValueW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
              L"WakeUp");
      v9 = v23;
      if ( v23 > 0 )
        v25 = (unsigned __int16)v23 | 0x80070000;
      else
        v25 = (unsigned int)v23;
      if ( tsched::IsErrorNotFound((tsched *)v25, v24) )
        goto LABEL_38;
      v22 = v9 <= 0;
      if ( !v9 )
        goto LABEL_38;
LABEL_27:
      if ( !v22 )
      {
        v9 = (unsigned __int16)v9;
        goto LABEL_29;
      }
LABEL_39:
      v13 = lpData;
      goto LABEL_40;
    }
  }
  v10 = RegDeleteKeyValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance",
          L"Activation Boundary");
  if ( v10 > 0 )
    v12 = (unsigned __int16)v10 | 0x80070000;
  else
    v12 = (unsigned int)v10;
  v9 = 0;
  if ( !tsched::IsErrorNotFound((tsched *)v12, v11) )
    v9 = v8;
  if ( !v9 )
    goto LABEL_15;
  if ( v9 > 0 )
    v9 = (unsigned __int16)v9 | 0x80070000;
  v13 = 0;
LABEL_40:
  SysFreeString(v13);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003a264  mov     rax, rsp
0x18003a267  mov     [rax+10h], rbx
0x18003a26b  mov     [rax+20h], rsi
0x18003a26f  mov     [rax+18h], r8
0x18003a273  mov     [rax+8], rcx
0x18003a277  push    rdi
0x18003a278  push    r14
0x18003a27a  push    r15
0x18003a27c  sub     rsp, 30h
0x18003a280  mov     rsi, rdx
0x18003a283  xor     ebx, ebx
0x18003a285  mov     [rax+8], rbx
0x18003a289  mov     [rax+18h], ebx
0x18003a28c  mov     r15d, 80070000h
0x18003a292  cmp     word ptr [rdx], 8
0x18003a296  jnz     short loc_18003A2F9
0x18003a298  mov     rdx, [rdx+8]
0x18003a29c  test    rdx, rdx
0x18003a29f  jz      short loc_18003A2F9
0x18003a2a1  lea     rcx, [rax+8]
0x18003a2a5  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18003a2aa  mov     rbx, [rsp+48h+bstr]
0x18003a2af  mov     rcx, rbx; bstr
0x18003a2b2  call    cs:__imp_SysStringByteLen
0x18003a2b8  mov     [rsp+48h+cbData], eax; cbData
0x18003a2bc  mov     [rsp+48h+lpData], rbx; lpData
0x18003a2c1  mov     r9d, 1; dwType
0x18003a2c7  lea     r8, ValueName; "Activation Boundary"
0x18003a2ce  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003a2d5  mov     r14, 0FFFFFFFF80000002h
0x18003a2dc  mov     rcx, r14; hKey
0x18003a2df  call    cs:__imp_RegSetKeyValueW
0x18003a2e5  mov     edi, eax
0x18003a2e7  test    eax, eax
0x18003a2e9  jz      short loc_18003A349
0x18003a2eb  jle     loc_18003A45D
0x18003a2f1  movzx   edi, ax
0x18003a2f4  jmp     loc_18003A3E9
0x18003a2f9  lea     r8, ValueName; "Activation Boundary"
0x18003a300  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003a307  mov     r14, 0FFFFFFFF80000002h
0x18003a30e  mov     rcx, r14; hKey
0x18003a311  call    cs:__imp_RegDeleteKeyValueW
0x18003a317  mov     r8d, eax
0x18003a31a  test    eax, eax
0x18003a31c  jg      short loc_18003A322
0x18003a31e  mov     ecx, eax
0x18003a320  jmp     short loc_18003A329
0x18003a322  movzx   ecx, r8w
0x18003a326  or      ecx, r15d; this
0x18003a329  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18003a32e  xor     edi, edi
0x18003a330  test    al, al
0x18003a332  cmovz   edi, r8d
0x18003a336  test    edi, edi
0x18003a338  jz      short loc_18003A349
0x18003a33a  jle     short loc_18003A342
0x18003a33c  movzx   edi, di
0x18003a33f  or      edi, r15d
0x18003a342  xor     ecx, ecx
0x18003a344  jmp     loc_18003A460
0x18003a349  cmp     word ptr [rsi+18h], 8
0x18003a34e  jnz     short loc_18003A3AA
0x18003a350  mov     rdx, [rsi+20h]
0x18003a354  test    rdx, rdx
0x18003a357  jz      short loc_18003A3AA
0x18003a359  lea     rcx, [rsp+48h+bstr]
0x18003a35e  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18003a363  mov     rbx, [rsp+48h+bstr]
0x18003a368  mov     rcx, rbx; bstr
0x18003a36b  call    cs:__imp_SysStringByteLen
0x18003a371  mov     [rsp+48h+cbData], eax; cbData
0x18003a375  mov     [rsp+48h+lpData], rbx; lpData
0x18003a37a  mov     r9d, 1; dwType
0x18003a380  lea     r8, aRandomDelay; "Random Delay"
0x18003a387  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003a38e  mov     rcx, r14; hKey
0x18003a391  call    cs:__imp_RegSetKeyValueW
0x18003a397  test    eax, eax
0x18003a399  jz      short loc_18003A3EE
0x18003a39b  jle     short loc_18003A3A3
0x18003a39d  movzx   eax, ax
0x18003a3a0  or      eax, r15d
0x18003a3a3  mov     edi, eax
0x18003a3a5  jmp     loc_18003A45D
0x18003a3aa  lea     r8, aRandomDelay; "Random Delay"
0x18003a3b1  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003a3b8  mov     rcx, r14; hKey
0x18003a3bb  call    cs:__imp_RegDeleteKeyValueW
0x18003a3c1  mov     r8d, eax
0x18003a3c4  test    eax, eax
0x18003a3c6  jg      short loc_18003A3CC
0x18003a3c8  mov     ecx, eax
0x18003a3ca  jmp     short loc_18003A3D3
0x18003a3cc  movzx   ecx, r8w
0x18003a3d0  or      ecx, r15d; this
0x18003a3d3  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18003a3d8  xor     edi, edi
0x18003a3da  test    al, al
0x18003a3dc  cmovz   edi, r8d
0x18003a3e0  test    edi, edi
0x18003a3e2  jz      short loc_18003A3EE
0x18003a3e4  jle     short loc_18003A45D
0x18003a3e6  movzx   edi, di
0x18003a3e9  or      edi, r15d
0x18003a3ec  jmp     short loc_18003A45D
0x18003a3ee  lea     r8, aWakeup; "WakeUp"
0x18003a3f5  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003a3fc  mov     rcx, r14; hKey
0x18003a3ff  cmp     word ptr [rsi+30h], 0Bh
0x18003a404  jnz     short loc_18003A438
0x18003a406  xor     eax, eax
0x18003a408  cmp     word ptr [rsi+38h], 0FFFFh
0x18003a40d  setz    al
0x18003a410  mov     [rsp+48h+Data], eax
0x18003a414  mov     r9d, 4; dwType
0x18003a41a  mov     [rsp+48h+cbData], r9d; cbData
0x18003a41f  lea     rax, [rsp+48h+Data]
0x18003a424  mov     [rsp+48h+lpData], rax; lpData
0x18003a429  call    cs:__imp_RegSetKeyValueW
0x18003a42f  test    eax, eax
0x18003a431  jz      short loc_18003A45B
0x18003a433  jmp     loc_18003A39B
0x18003a438  call    cs:__imp_RegDeleteKeyValueW
0x18003a43e  mov     edi, eax
0x18003a440  test    eax, eax
0x18003a442  jg      short loc_18003A448
0x18003a444  mov     ecx, eax
0x18003a446  jmp     short loc_18003A44E
0x18003a448  movzx   ecx, di
0x18003a44b  or      ecx, r15d; this
0x18003a44e  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x18003a453  test    al, al
0x18003a455  jnz     short loc_18003A45B
0x18003a457  test    edi, edi
0x18003a459  jnz     short loc_18003A3E4
0x18003a45b  xor     edi, edi
0x18003a45d  mov     rcx, rbx; bstrString
0x18003a460  call    cs:__imp_SysFreeString
0x18003a466  mov     eax, edi
0x18003a468  mov     rbx, [rsp+48h+arg_8]
0x18003a46d  mov     rsi, [rsp+48h+arg_18]
0x18003a472  add     rsp, 30h
0x18003a476  pop     r15
0x18003a478  pop     r14
0x18003a47a  pop     rdi
0x18003a47b  retn
```
