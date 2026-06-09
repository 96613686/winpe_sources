# VmExdiServer::GetTargetInfo(_GLOBAL_TARGET_INFO_STRUCT *)

- ea: `0x140188f80`
- end: `0x140189068`
- name: `?GetTargetInfo@VmExdiServer@@UEAAJPEAU_GLOBAL_TARGET_INFO_STRUCT@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(VmExdiServer *__hidden this, struct _GLOBAL_TARGET_INFO_STRUCT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140188f80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140188ff1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14018900b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140188ff1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14018900b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140189025`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14018903e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140189025`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14018903e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140188fb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140188fc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140188fb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140188fc9`

## pseudocode

```c
__int64 __fastcall VmExdiServer::GetTargetInfo(VmExdiServer *this, struct _GLOBAL_TARGET_INFO_STRUCT *a2)
{
  LPVOID v3; // rax
  void *v4; // rcx
  unsigned int v5; // edi
  void *v6; // rcx

  if ( a2 )
  {
    *(_QWORD *)a2 = 0;
    *((_QWORD *)a2 + 1) = 0;
    *((_QWORD *)a2 + 2) = 0;
    *((_QWORD *)a2 + 3) = 0;
    *((_QWORD *)a2 + 4) = 0;
    *((_DWORD *)a2 + 10) = 0;
    *((_QWORD *)a2 + 6) = CoTaskMemAlloc(0x20u);
    v3 = CoTaskMemAlloc(0x1Eu);
    v4 = (void *)*((_QWORD *)a2 + 6);
    *((_QWORD *)a2 + 7) = v3;
    if ( v4 && v3 )
    {
      _o_wcscpy_s(v4, 16, L"Virtual Machine");
      _o_wcscpy_s(*((_QWORD *)a2 + 7), 15, L"VM EXDI Driver");
      return 0;
    }
    else
    {
      v5 = -528351218;
      if ( v4 )
      {
        CoTaskMemFree(v4);
        *((_QWORD *)a2 + 6) = 0;
      }
      v6 = (void *)*((_QWORD *)a2 + 7);
      if ( v6 )
      {
        CoTaskMemFree(v6);
        *((_QWORD *)a2 + 7) = 0;
      }
    }
  }
  else
  {
    return (unsigned int)-528351145;
  }
  return v5;
}

```

## disassembly

```asm
0x140188f80  mov     [rsp+arg_0], rbx
0x140188f85  mov     [rsp+arg_8], rsi
0x140188f8a  push    rdi
0x140188f8b  sub     rsp, 20h
0x140188f8f  xor     esi, esi
0x140188f91  mov     rbx, rdx
0x140188f94  test    rdx, rdx
0x140188f97  jz      loc_140189050
0x140188f9d  lea     ecx, [rsi+20h]; cb
0x140188fa0  mov     [rdx], rsi
0x140188fa3  mov     [rdx+8], rsi
0x140188fa7  mov     [rdx+10h], rsi
0x140188fab  mov     [rdx+18h], rsi
0x140188faf  mov     [rdx+20h], rsi
0x140188fb3  mov     [rdx+28h], esi
0x140188fb6  call    cs:__imp_CoTaskMemAlloc
0x140188fbd  nop     dword ptr [rax+rax+00h]
0x140188fc2  lea     ecx, [rsi+1Eh]; cb
0x140188fc5  mov     [rbx+30h], rax
0x140188fc9  call    cs:__imp_CoTaskMemAlloc
0x140188fd0  nop     dword ptr [rax+rax+00h]
0x140188fd5  mov     rcx, [rbx+30h]; pv
0x140188fd9  mov     [rbx+38h], rax
0x140188fdd  test    rcx, rcx
0x140188fe0  jz      short loc_14018901B
0x140188fe2  test    rax, rax
0x140188fe5  jz      short loc_14018901B
0x140188fe7  lea     r8, aVirtualMachine_1; "Virtual Machine"
0x140188fee  lea     edx, [rsi+10h]
0x140188ff1  call    cs:__imp__o_wcscpy_s
0x140188ff8  nop     dword ptr [rax+rax+00h]
0x140188ffd  mov     rcx, [rbx+38h]
0x140189001  lea     r8, aVmExdiDriver; "VM EXDI Driver"
0x140189008  lea     edx, [rsi+0Fh]
0x14018900b  call    cs:__imp__o_wcscpy_s
0x140189012  nop     dword ptr [rax+rax+00h]
0x140189017  mov     edi, esi
0x140189019  jmp     short loc_140189055
0x14018901b  mov     edi, 0E082000Eh
0x140189020  test    rcx, rcx
0x140189023  jz      short loc_140189035
0x140189025  call    cs:__imp_CoTaskMemFree
0x14018902c  nop     dword ptr [rax+rax+00h]
0x140189031  mov     [rbx+30h], rsi
0x140189035  mov     rcx, [rbx+38h]; pv
0x140189039  test    rcx, rcx
0x14018903c  jz      short loc_140189055
0x14018903e  call    cs:__imp_CoTaskMemFree
0x140189045  nop     dword ptr [rax+rax+00h]
0x14018904a  mov     [rbx+38h], rsi
0x14018904e  jmp     short loc_140189055
0x140189050  mov     edi, 0E0820057h
0x140189055  mov     rbx, [rsp+28h+arg_0]
0x14018905a  mov     eax, edi
0x14018905c  mov     rsi, [rsp+28h+arg_8]
0x140189061  add     rsp, 20h
0x140189065  pop     rdi
0x140189066  retn
```
