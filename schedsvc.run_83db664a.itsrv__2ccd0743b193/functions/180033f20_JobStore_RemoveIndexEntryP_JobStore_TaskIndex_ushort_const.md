# JobStore::RemoveIndexEntryP(JobStore::TaskIndex,ushort const *)

- ea: `0x180033f20`
- end: `0x1800340c2`
- name: `?RemoveIndexEntryP@JobStore@@AEBAJW4TaskIndex@1@PEBG@Z`
- size: `418`
- prototype: `int __high(enum JobStore::TaskIndex, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180031cf0`

## callees

- `0x18002123c`
- `0x18002db40`
- `0x180033f20`
- `0x18004bde4`
- `0x180059140`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180034013`
- `OLEAUT32!__imp_SysFreeString` at `0x1800340a6`
- `OLEAUT32!__imp_SysFreeString` at `0x180034013`
- `OLEAUT32!__imp_SysFreeString` at `0x1800340a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180034034`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180034034`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033f9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033f9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034092`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034092`

## string_xrefs

- `0x180033f6a`: `TaskCache\Boot`
- `0x180033f61`: `TaskCache\Logon`
- `0x180033f58`: `TaskCache\Plain`
- `0x180033f4f`: `TaskCache\Maintenance`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JobStore::RemoveIndexEntryP(__int64 a1, int a2, const WCHAR *a3)
{
  WCHAR *v5; // rbx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  const wchar_t *v9; // rdx
  LSTATUS v10; // eax
  int v11; // edx
  unsigned int v12; // edi
  _QWORD *v13; // rcx
  int v14; // edx
  LSTATUS v16; // eax
  int v17; // edx
  WCHAR *v18; // [rsp+50h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v5 = 0;
  v18 = 0;
  v6 = a2 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        if ( v8 != 1 )
          goto LABEL_10;
        v9 = L"TaskCache\\Maintenance";
      }
      else
      {
        v9 = L"TaskCache\\Plain";
      }
    }
    else
    {
      v9 = L"TaskCache\\Logon";
    }
  }
  else
  {
    v9 = L"TaskCache\\Boot";
  }
  ATL::CComBSTR::operator=(&v18, v9);
  v5 = v18;
LABEL_10:
  hKey = 0;
  v10 = RegOpenKeyExW(*(HKEY *)(a1 + 16), v5, 0, 0x20019u, &hKey);
  v12 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v12 = (unsigned __int16)v10 | 0x80070000;
    if ( tsched::IsErrorNotFound((tsched *)v12, v11) )
      goto LABEL_19;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_19;
    }
    v14 = 61;
LABEL_18:
    WPP_SF_Sd(v13[2], v14, (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids, (_DWORD)a3, v12);
LABEL_19:
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    SysFreeString(v5);
    return v12;
  }
  v16 = RegDeleteKeyExW(hKey, a3, 0, 0);
  v12 = v16;
  if ( v16 )
  {
    if ( v16 > 0 )
      v12 = (unsigned __int16)v16 | 0x80070000;
    if ( tsched::IsErrorNotFound((tsched *)v12, v17) )
      goto LABEL_19;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_19;
    }
    v14 = 62;
    goto LABEL_18;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  SysFreeString(v5);
  return 0;
}

```

## disassembly

```asm
0x180033f20  mov     [rsp+arg_8], rbx
0x180033f25  push    rbp
0x180033f26  push    rsi
0x180033f27  push    rdi
0x180033f28  sub     rsp, 30h
0x180033f2c  mov     rsi, r8
0x180033f2f  mov     rdi, rcx
0x180033f32  xor     ebp, ebp
0x180033f34  mov     ebx, ebp
0x180033f36  mov     [rsp+48h+arg_0], rbx
0x180033f3b  sub     edx, 1
0x180033f3e  jz      short loc_180033F6A
0x180033f40  sub     edx, 1
0x180033f43  jz      short loc_180033F61
0x180033f45  sub     edx, 1
0x180033f48  jz      short loc_180033F58
0x180033f4a  cmp     edx, 1
0x180033f4d  jnz     short loc_180033F80
0x180033f4f  lea     rdx, aTaskcacheMaint; "TaskCache\\Maintenance"
0x180033f56  jmp     short loc_180033F71
0x180033f58  lea     rdx, aTaskcachePlain; "TaskCache\\Plain"
0x180033f5f  jmp     short loc_180033F71
0x180033f61  lea     rdx, aTaskcacheLogon; "TaskCache\\Logon"
0x180033f68  jmp     short loc_180033F71
0x180033f6a  lea     rdx, aTaskcacheBoot; "TaskCache\\Boot"
0x180033f71  lea     rcx, [rsp+48h+arg_0]
0x180033f76  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180033f7b  mov     rbx, [rsp+48h+arg_0]
0x180033f80  mov     [rsp+48h+hKey], rbp
0x180033f85  lea     rax, [rsp+48h+hKey]
0x180033f8a  mov     [rsp+48h+phkResult], rax; phkResult
0x180033f8f  mov     r9d, 20019h; samDesired
0x180033f95  xor     r8d, r8d; ulOptions
0x180033f98  mov     rdx, rbx; lpSubKey
0x180033f9b  mov     rcx, [rdi+10h]; hKey
0x180033f9f  call    cs:__imp_RegOpenKeyExW
0x180033fa6  nop     dword ptr [rax+rax+00h]
0x180033fab  mov     edi, eax
0x180033fad  test    eax, eax
0x180033faf  jz      short loc_180034026
0x180033fb1  jle     short loc_180033FBC
0x180033fb3  movzx   edi, ax
0x180033fb6  or      edi, 80070000h
0x180033fbc  mov     ecx, edi; this
0x180033fbe  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180033fc3  test    al, al
0x180033fc5  jnz     short loc_180034005
0x180033fc7  lea     rax, WPP_GLOBAL_Control
0x180033fce  mov     rcx, cs:WPP_GLOBAL_Control
0x180033fd5  cmp     rcx, rax
0x180033fd8  jz      short loc_180034005
0x180033fda  test    dword ptr [rcx+1Ch], 40000h
0x180033fe1  jz      short loc_180034005
0x180033fe3  cmp     byte ptr [rcx+19h], 2
0x180033fe7  jb      short loc_180034005
0x180033fe9  mov     edx, 3Dh ; '='
0x180033fee  mov     dword ptr [rsp+48h+phkResult], edi
0x180033ff2  mov     r9, rsi
0x180033ff5  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180033ffc  mov     rcx, [rcx+10h]
0x180034000  call    WPP_SF_Sd
0x180034005  lea     rcx, [rsp+48h+hKey]; this
0x18003400a  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18003400f  nop
0x180034010  mov     rcx, rbx; bstrString
0x180034013  call    cs:__imp_SysFreeString
0x18003401a  nop     dword ptr [rax+rax+00h]
0x18003401f  mov     eax, edi
0x180034021  jmp     loc_1800340B4
0x180034026  xor     r9d, r9d; Reserved
0x180034029  xor     r8d, r8d; samDesired
0x18003402c  mov     rdx, rsi; lpSubKey
0x18003402f  mov     rcx, [rsp+48h+hKey]; hKey
0x180034034  call    cs:__imp_RegDeleteKeyExW
0x18003403b  nop     dword ptr [rax+rax+00h]
0x180034040  mov     edi, eax
0x180034042  test    eax, eax
0x180034044  jz      short loc_180034088
0x180034046  jle     short loc_180034051
0x180034048  movzx   edi, ax
0x18003404b  or      edi, 80070000h
0x180034051  mov     ecx, edi; this
0x180034053  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180034058  test    al, al
0x18003405a  jnz     short loc_180034005
0x18003405c  lea     rax, WPP_GLOBAL_Control
0x180034063  mov     rcx, cs:WPP_GLOBAL_Control
0x18003406a  cmp     rcx, rax
0x18003406d  jz      short loc_180034005
0x18003406f  test    dword ptr [rcx+1Ch], 40000h
0x180034076  jz      short loc_180034005
0x180034078  cmp     byte ptr [rcx+19h], 2
0x18003407c  jb      short loc_180034005
0x18003407e  mov     edx, 3Eh ; '>'
0x180034083  jmp     loc_180033FEE
0x180034088  mov     rcx, [rsp+48h+hKey]; hKey
0x18003408d  test    rcx, rcx
0x180034090  jz      short loc_1800340A3
0x180034092  call    cs:__imp_RegCloseKey
0x180034099  nop     dword ptr [rax+rax+00h]
0x18003409e  mov     [rsp+48h+hKey], rbp
0x1800340a3  mov     rcx, rbx; bstrString
0x1800340a6  call    cs:__imp_SysFreeString
0x1800340ad  nop     dword ptr [rax+rax+00h]
0x1800340b2  xor     eax, eax
0x1800340b4  mov     rbx, [rsp+48h+arg_8]
0x1800340b9  add     rsp, 30h
0x1800340bd  pop     rdi
0x1800340be  pop     rsi
0x1800340bf  pop     rbp
0x1800340c0  retn
```
