# CRegMonitor::StartSubkeyMonitoring(void)

- ea: `0x18002c6ac`
- end: `0x18002c778`
- name: `?StartSubkeyMonitoring@CRegMonitor@@QEAAJXZ`
- size: `204`
- prototype: `__int64 __fastcall(CRegMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180020ee4`

## callees

- `0x18002c6ac`
- `0x18002c780`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002c72c`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002c72c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c6f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c6f5`

## pseudocode

```c
__int64 __fastcall CRegMonitor::StartSubkeyMonitoring(CRegMonitor *this)
{
  const WCHAR *v1; // rdx
  HKEY *v3; // rsi
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  LSTATUS v6; // eax

  v1 = (const WCHAR *)*((_QWORD *)this + 3);
  if ( !v1 || !*((_QWORD *)this + 2) )
  {
    v5 = -2147418113;
    goto LABEL_15;
  }
  v3 = (HKEY *)((char *)this + 8);
  if ( *((_DWORD *)this + 1) )
  {
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0x10u, (PHKEY)this + 1);
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( (v5 & 0x80000000) == 0 )
    {
      *((_DWORD *)this + 1) = 0;
      if ( v5 )
        return v5;
      goto LABEL_8;
    }
    if ( v5 == -2147024894 )
    {
      v5 = 1;
      *((_DWORD *)this + 1) = 1;
      return v5;
    }
LABEL_15:
    CRegMonitor::StopSubkeyMonitoring(this);
    return v5;
  }
LABEL_8:
  v6 = RegNotifyChangeKeyValue(*v3, 1, 1u, *((HANDLE *)this + 2), 1);
  v5 = v6;
  if ( v6 > 0 )
    v5 = (unsigned __int16)v6 | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_15;
  return v5;
}

```

## disassembly

```asm
0x18002c6ac  mov     [rsp+arg_0], rbx
0x18002c6b1  mov     [rsp+arg_8], rsi
0x18002c6b6  push    rdi
0x18002c6b7  sub     rsp, 30h
0x18002c6bb  mov     rdx, [rcx+18h]; lpSubKey
0x18002c6bf  mov     rdi, rcx
0x18002c6c2  test    rdx, rdx
0x18002c6c5  jz      loc_18002C759
0x18002c6cb  cmp     qword ptr [rcx+10h], 0
0x18002c6d0  jz      loc_18002C759
0x18002c6d6  cmp     dword ptr [rcx+4], 0
0x18002c6da  lea     rsi, [rcx+8]
0x18002c6de  jz      short loc_18002C717
0x18002c6e0  mov     r9d, 10h; samDesired
0x18002c6e6  mov     [rsp+38h+phkResult], rsi; phkResult
0x18002c6eb  xor     r8d, r8d; ulOptions
0x18002c6ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c6f5  call    cs:__imp_RegOpenKeyExW
0x18002c6fb  mov     ebx, eax
0x18002c6fd  test    eax, eax
0x18002c6ff  jle     short loc_18002C70A
0x18002c701  movzx   ebx, ax
0x18002c704  or      ebx, 80070000h
0x18002c70a  test    ebx, ebx
0x18002c70c  js      short loc_18002C747
0x18002c70e  mov     dword ptr [rdi+4], 0
0x18002c715  jnz     short loc_18002C766
0x18002c717  mov     r9, [rdi+10h]; hEvent
0x18002c71b  mov     ebx, 1
0x18002c720  mov     rcx, [rsi]; hKey
0x18002c723  mov     r8d, ebx; dwNotifyFilter
0x18002c726  mov     edx, ebx; bWatchSubtree
0x18002c728  mov     dword ptr [rsp+38h+phkResult], ebx; fAsynchronous
0x18002c72c  call    cs:__imp_RegNotifyChangeKeyValue
0x18002c732  mov     ebx, eax
0x18002c734  test    eax, eax
0x18002c736  jle     short loc_18002C741
0x18002c738  movzx   ebx, ax
0x18002c73b  or      ebx, 80070000h
0x18002c741  test    ebx, ebx
0x18002c743  jns     short loc_18002C766
0x18002c745  jmp     short loc_18002C75E
0x18002c747  cmp     ebx, 80070002h
0x18002c74d  jnz     short loc_18002C75E
0x18002c74f  mov     ebx, 1
0x18002c754  mov     [rdi+4], ebx
0x18002c757  jmp     short loc_18002C766
0x18002c759  mov     ebx, 8000FFFFh
0x18002c75e  mov     rcx, rdi; this
0x18002c761  call    ?StopSubkeyMonitoring@CRegMonitor@@QEAAXXZ; CRegMonitor::StopSubkeyMonitoring(void)
0x18002c766  mov     rsi, [rsp+38h+arg_8]
0x18002c76b  mov     eax, ebx
0x18002c76d  mov     rbx, [rsp+38h+arg_0]
0x18002c772  add     rsp, 30h
0x18002c776  pop     rdi
0x18002c777  retn
```
