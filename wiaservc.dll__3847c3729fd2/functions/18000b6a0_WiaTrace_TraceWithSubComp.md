# WiaTrace_TraceWithSubComp

- ea: `0x18000b6a0`
- end: `0x18000b77a`
- name: `WiaTrace_TraceWithSubComp`
- size: `218`
- prototype: `__int64(_QWORD, const char *, ...)`
- caller_count: `156`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002db4`
- `0x1800033f4`
- `0x180004790`
- `0x1800049e0`
- `0x180004dbc`
- `0x180004ff8`
- `0x18000557c`
- `0x180005a48`
- `0x1800060d0`
- `0x180006b88`
- `0x180006f9c`
- `0x1800070fc`
- `0x180007324`
- `0x180007a10`
- `0x180007b18`
- `0x180007c20`
- `0x180007e00`
- `0x180007fd0`
- `0x18000813c`
- `0x1800085b0`
- `0x180008930`
- `0x180008b18`
- `0x180008cac`
- `0x180008ee0`
- `0x180009040`
- `0x1800095e8`
- `0x180009b80`
- `0x18000a538`
- `0x18000a9e0`
- `0x18000ac58`
- `0x18000b780`
- `0x18000c040`
- `0x18000e080`
- `0x18000ea00`
- `0x18000ecf0`
- `0x18000f88c`
- `0x18000fc60`
- `0x180010340`
- `0x180010730`
- `0x180010f0c`
- `0x1800124b0`
- `0x180012fd0`
- `0x1800138a8`
- `0x180013c80`
- `0x1800147d0`
- `0x180014a70`
- `0x1800150c8`
- `0x180015f90`
- `0x180016ab8`
- `0x18001828c`

## callees

- `0x180004680`
- `0x18000b6a0`
- `0x180015780`
- `0x180015910`
- `0x18002ef7c`
- `0x180033cc0`
- `0x180034658`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18000b736`
- `KERNEL32!GetCurrentProcessId` at `0x18000b736`
- `KERNEL32!GetCurrentThreadId` at `0x18000b73f`
- `KERNEL32!GetCurrentThreadId` at `0x18000b73f`

## pseudocode

```c
_DWORD *WiaTrace_TraceWithSubComp(int a1, const char *a2, ...)
{
  _DWORD *v2; // rbx
  WiaTrcLib *v4; // rcx
  char *v5; // r8
  char pszDest[512]; // [rsp+30h] [rbp-228h] BYREF
  va_list argList; // [rsp+270h] [rbp+18h] BYREF

  va_start(argList, a2);
  v2 = 0;
  if ( (g_WiaTrace_ulFlags & 2) != 0 )
  {
    v2 = WiaTrcLib::Alloc((WiaTrcLib *)0x40, (unsigned __int64)a2);
    if ( v2 )
    {
      memset_0(pszDest, 0, sizeof(pszDest));
      memset_0(v2, 0, 0x40u);
      StringCchVPrintfA(pszDest, 0x200u, a2, argList);
      v2[13] = a1;
      v2[3] = GetCurrentProcessId();
      v2[4] = GetCurrentThreadId();
      v2[14] = WiaTrcLib::GetCurrentIndentLevel(v4);
      WiaTrcLib::AddToString((WiaTrcLib *)v2, (char **)pszDest, v5);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000b6a0  mov     [rsp+pszFormat], rdx
0x18000b6a5  mov     qword ptr [rsp+argList], r8
0x18000b6aa  mov     [rsp+arg_18], r9
0x18000b6af  push    rbx
0x18000b6b0  push    rdi
0x18000b6b1  sub     rsp, 248h
0x18000b6b8  mov     rax, cs:__security_cookie
0x18000b6bf  xor     rax, rsp
0x18000b6c2  mov     [rsp+258h+var_28], rax
0x18000b6ca  xor     ebx, ebx
0x18000b6cc  mov     edi, ecx
0x18000b6ce  test    byte ptr cs:g_WiaTrace_ulFlags, 2
0x18000b6d5  jz      loc_18000B75D
0x18000b6db  lea     ecx, [rbx+40h]; this
0x18000b6de  call    ?Alloc@WiaTrcLib@@YAPEAX_K@Z; WiaTrcLib::Alloc(unsigned __int64)
0x18000b6e3  mov     rbx, rax
0x18000b6e6  test    rax, rax
0x18000b6e9  jz      short loc_18000B75D
0x18000b6eb  xor     edx, edx; Val
0x18000b6ed  lea     rcx, [rsp+258h+pszDest]; void *
0x18000b6f2  mov     r8d, 200h; Size
0x18000b6f8  call    memset_0
0x18000b6fd  xor     edx, edx; Val
0x18000b6ff  mov     rcx, rbx; void *
0x18000b702  lea     r8d, [rdx+40h]; Size
0x18000b706  call    memset_0
0x18000b70b  mov     r8, [rsp+258h+pszFormat]; pszFormat
0x18000b713  lea     r9, [rsp+258h+argList]; argList
0x18000b71b  mov     edx, 200h; cchDest
0x18000b720  mov     [rsp+258h+var_238], 0
0x18000b729  lea     rcx, [rsp+258h+pszDest]; pszDest
0x18000b72e  call    StringCchVPrintfA
0x18000b733  mov     [rbx+34h], edi
0x18000b736  call    cs:__imp_GetCurrentProcessId
0x18000b73c  mov     [rbx+0Ch], eax
0x18000b73f  call    cs:__imp_GetCurrentThreadId
0x18000b745  mov     [rbx+10h], eax
0x18000b748  call    ?GetCurrentIndentLevel@WiaTrcLib@@YAKXZ; WiaTrcLib::GetCurrentIndentLevel(void)
0x18000b74d  lea     rdx, [rsp+258h+pszDest]; char **
0x18000b752  mov     [rbx+38h], eax
0x18000b755  mov     rcx, rbx; this
0x18000b758  call    ?AddToString@WiaTrcLib@@YAJPEAPEADPEAD@Z; WiaTrcLib::AddToString(char * *,char *)
0x18000b75d  mov     rax, rbx
0x18000b760  mov     rcx, [rsp+258h+var_28]
0x18000b768  xor     rcx, rsp; StackCookie
0x18000b76b  call    __security_check_cookie
0x18000b770  add     rsp, 248h
0x18000b777  pop     rdi
0x18000b778  pop     rbx
0x18000b779  retn
```
