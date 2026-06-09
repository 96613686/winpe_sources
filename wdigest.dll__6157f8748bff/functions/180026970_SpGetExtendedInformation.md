# SpGetExtendedInformation

- ea: `0x180026970`
- end: `0x180026abc`
- name: `SpGetExtendedInformation`
- size: `332`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800061a0`
- `0x180009770`
- `0x180011fec`
- `0x1800185b8`
- `0x180026970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a3f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180026a23`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180026a23`

## string_xrefs

- `0x180026a1c`: `%SystemRoot%\SysWOW64\wdigest.dll`

## pseudocode

```c
__int64 __fastcall SpGetExtendedInformation(int a1, _QWORD *a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 Memory; // rax
  _WORD *v7; // rdi
  DWORD v8; // eax
  DWORD LastError; // eax
  __int16 v10; // ax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 != 4 )
  {
    v5 = -2146893054;
    goto LABEL_17;
  }
  Memory = DigestAllocateMemory(0x240u);
  v7 = (_WORD *)Memory;
  if ( Memory )
  {
    *(_DWORD *)Memory = 4;
    *(_QWORD *)(Memory + 16) = Memory + 56;
    v8 = ExpandEnvironmentStringsW(L"%SystemRoot%\\SysWOW64\\wdigest.dll", (LPWSTR)(Memory + 56), 0x104u);
    if ( v8 )
    {
      v10 = 2 * v8;
      v5 = 0;
      v7[4] = v10;
      v7[5] = v10 + 2;
      *a2 = v7;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids, LastError);
      }
      DigestFreeMemory(v7);
      v5 = -1073741670;
    }
    goto LABEL_16;
  }
  v5 = -1073741670;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids);
LABEL_16:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_17:
  if ( v4 != &WPP_GLOBAL_Control && *((char *)v4 + 28) < 0 )
    WPP_SF_d(v4[2], 37, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180026970  push    rbx
0x180026972  push    rbp
0x180026973  push    rsi
0x180026974  push    rdi
0x180026975  sub     rsp, 28h
0x180026979  mov     rsi, rdx
0x18002697c  mov     ebx, ecx
0x18002697e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026985  lea     rbp, WPP_GLOBAL_Control
0x18002698c  cmp     rcx, rbp
0x18002698f  jz      short loc_1800269B3
0x180026991  test    byte ptr [rcx+1Ch], 80h
0x180026995  jz      short loc_1800269B3
0x180026997  mov     rcx, [rcx+10h]
0x18002699b  lea     r8, WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids
0x1800269a2  mov     edx, 22h ; '"'
0x1800269a7  call    WPP_SF_
0x1800269ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269b3  cmp     ebx, 4
0x1800269b6  jz      short loc_1800269C2
0x1800269b8  mov     ebx, 80090302h
0x1800269bd  jmp     loc_180026A8E
0x1800269c2  mov     ecx, 240h; Size
0x1800269c7  call    DigestAllocateMemory
0x1800269cc  mov     rdi, rax
0x1800269cf  test    rax, rax
0x1800269d2  jnz     short loc_180026A08
0x1800269d4  mov     ebx, 0C000009Ah
0x1800269d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269e0  cmp     rcx, rbp
0x1800269e3  jz      loc_180026AB1
0x1800269e9  test    byte ptr [rcx+1Ch], 1
0x1800269ed  jz      loc_180026A8E
0x1800269f3  mov     rcx, [rcx+10h]
0x1800269f7  lea     edx, [rax+23h]
0x1800269fa  lea     r8, WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids
0x180026a01  call    WPP_SF_
0x180026a06  jmp     short loc_180026A87
0x180026a08  lea     rdx, [rax+38h]; lpDst
0x180026a0c  mov     dword ptr [rax], 4
0x180026a12  mov     r8d, 104h; nSize
0x180026a18  mov     [rax+10h], rdx
0x180026a1c  lea     rcx, aSystemrootSysw; "%SystemRoot%\\SysWOW64\\wdigest.dll"
0x180026a23  call    cs:__imp_ExpandEnvironmentStringsW
0x180026a29  test    eax, eax
0x180026a2b  jnz     short loc_180026A73
0x180026a2d  mov     rax, cs:WPP_GLOBAL_Control
0x180026a34  cmp     rax, rbp
0x180026a37  jz      short loc_180026A64
0x180026a39  test    byte ptr [rax+1Ch], 1
0x180026a3d  jz      short loc_180026A64
0x180026a3f  call    cs:__imp_GetLastError
0x180026a45  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a4c  lea     r8, WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids
0x180026a53  mov     edx, 24h ; '$'
0x180026a58  mov     r9d, eax
0x180026a5b  mov     rcx, [rcx+10h]
0x180026a5f  call    WPP_SF_d
0x180026a64  mov     rcx, rdi; hMem
0x180026a67  call    DigestFreeMemory
0x180026a6c  mov     ebx, 0C000009Ah
0x180026a71  jmp     short loc_180026A87
0x180026a73  add     ax, ax
0x180026a76  xor     ebx, ebx
0x180026a78  mov     [rdi+8], ax
0x180026a7c  add     ax, 2
0x180026a80  mov     [rdi+0Ah], ax
0x180026a84  mov     [rsi], rdi
0x180026a87  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a8e  cmp     rcx, rbp
0x180026a91  jz      short loc_180026AB1
0x180026a93  test    byte ptr [rcx+1Ch], 80h
0x180026a97  jz      short loc_180026AB1
0x180026a99  mov     rcx, [rcx+10h]
0x180026a9d  lea     r8, WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids
0x180026aa4  mov     edx, 25h ; '%'
0x180026aa9  mov     r9d, ebx
0x180026aac  call    WPP_SF_d
0x180026ab1  mov     eax, ebx
0x180026ab3  add     rsp, 28h
0x180026ab7  pop     rdi
0x180026ab8  pop     rsi
0x180026ab9  pop     rbp
0x180026aba  pop     rbx
0x180026abb  retn
```
