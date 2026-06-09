# VmExdiServer::GetTargetInfo(_GLOBAL_TARGET_INFO_STRUCT *)

- ea: `0x140199fd0`
- end: `0x14019a0b8`
- name: `?GetTargetInfo@VmExdiServer@@UEAAJPEAU_GLOBAL_TARGET_INFO_STRUCT@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(VmExdiServer *__hidden this, struct _GLOBAL_TARGET_INFO_STRUCT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140199fd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14019a041`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14019a05b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14019a041`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14019a05b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14019a006`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14019a019`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14019a006`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14019a019`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14019a075`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14019a08e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14019a075`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14019a08e`

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
0x140199fd0  mov     [rsp+arg_0], rbx
0x140199fd5  mov     [rsp+arg_8], rsi
0x140199fda  push    rdi
0x140199fdb  sub     rsp, 20h
0x140199fdf  xor     esi, esi
0x140199fe1  mov     rbx, rdx
0x140199fe4  test    rdx, rdx
0x140199fe7  jz      loc_14019A0A0
0x140199fed  lea     ecx, [rsi+20h]; cb
0x140199ff0  mov     [rdx], rsi
0x140199ff3  mov     [rdx+8], rsi
0x140199ff7  mov     [rdx+10h], rsi
0x140199ffb  mov     [rdx+18h], rsi
0x140199fff  mov     [rdx+20h], rsi
0x14019a003  mov     [rdx+28h], esi
0x14019a006  call    cs:__imp_CoTaskMemAlloc
0x14019a00d  nop     dword ptr [rax+rax+00h]
0x14019a012  lea     ecx, [rsi+1Eh]; cb
0x14019a015  mov     [rbx+30h], rax
0x14019a019  call    cs:__imp_CoTaskMemAlloc
0x14019a020  nop     dword ptr [rax+rax+00h]
0x14019a025  mov     rcx, [rbx+30h]; pv
0x14019a029  mov     [rbx+38h], rax
0x14019a02d  test    rcx, rcx
0x14019a030  jz      short loc_14019A06B
0x14019a032  test    rax, rax
0x14019a035  jz      short loc_14019A06B
0x14019a037  lea     r8, aVirtualMachine_1; "Virtual Machine"
0x14019a03e  lea     edx, [rsi+10h]
0x14019a041  call    cs:__imp__o_wcscpy_s
0x14019a048  nop     dword ptr [rax+rax+00h]
0x14019a04d  mov     rcx, [rbx+38h]
0x14019a051  lea     r8, aVmExdiDriver; "VM EXDI Driver"
0x14019a058  lea     edx, [rsi+0Fh]
0x14019a05b  call    cs:__imp__o_wcscpy_s
0x14019a062  nop     dword ptr [rax+rax+00h]
0x14019a067  mov     edi, esi
0x14019a069  jmp     short loc_14019A0A5
0x14019a06b  mov     edi, 0E082000Eh
0x14019a070  test    rcx, rcx
0x14019a073  jz      short loc_14019A085
0x14019a075  call    cs:__imp_CoTaskMemFree
0x14019a07c  nop     dword ptr [rax+rax+00h]
0x14019a081  mov     [rbx+30h], rsi
0x14019a085  mov     rcx, [rbx+38h]; pv
0x14019a089  test    rcx, rcx
0x14019a08c  jz      short loc_14019A0A5
0x14019a08e  call    cs:__imp_CoTaskMemFree
0x14019a095  nop     dword ptr [rax+rax+00h]
0x14019a09a  mov     [rbx+38h], rsi
0x14019a09e  jmp     short loc_14019A0A5
0x14019a0a0  mov     edi, 0E0820057h
0x14019a0a5  mov     rbx, [rsp+28h+arg_0]
0x14019a0aa  mov     eax, edi
0x14019a0ac  mov     rsi, [rsp+28h+arg_8]
0x14019a0b1  add     rsp, 20h
0x14019a0b5  pop     rdi
0x14019a0b6  retn
```
