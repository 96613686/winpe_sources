# WiaTrace_TraceWithSubCompTraceLevel

- ea: `0x18000d7b0`
- end: `0x18000da08`
- name: `WiaTrace_TraceWithSubCompTraceLevel`
- size: `600`
- prototype: `__int64(_QWORD, _QWORD, const char *, ...)`
- caller_count: `196`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001cd4`
- `0x180002db4`
- `0x1800030f0`
- `0x1800033f4`
- `0x18000426c`
- `0x180004948`
- `0x180004aa8`
- `0x180004f60`
- `0x180004ff8`
- `0x18000557c`
- `0x180005f04`
- `0x180006040`
- `0x1800060d0`
- `0x18000645c`
- `0x180006740`
- `0x180006d20`
- `0x180007324`
- `0x180007c20`
- `0x18000813c`
- `0x1800085b0`
- `0x180008ee0`
- `0x180009040`
- `0x180009364`
- `0x1800095e8`
- `0x180009b80`
- `0x18000a200`
- `0x18000a538`
- `0x18000a6b4`
- `0x18000ab74`
- `0x18000b780`
- `0x18000bc50`
- `0x18000c040`
- `0x18000ce90`
- `0x18000de60`
- `0x18000e080`
- `0x18000e810`
- `0x18000ea00`
- `0x18000ecf0`
- `0x18000fdf4`
- `0x180010a28`
- `0x180010f0c`
- `0x180011c20`
- `0x180011f6c`
- `0x180012330`
- `0x1800124b0`
- `0x1800129fc`
- `0x180012fd0`
- `0x18001358c`
- `0x180013944`
- `0x180013c80`

## callees

- `0x18000d7b0`
- `0x180033cc0`
- `0x180034658`
- `0x180034708`
- `0x180039b9c`
- `0x180078010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000d974`
- `KERNEL32!HeapFree` at `0x18000d974`
- `KERNEL32!GetProcessHeap` at `0x18000d7f0`
- `KERNEL32!GetProcessHeap` at `0x18000d8eb`
- `KERNEL32!GetProcessHeap` at `0x18000d966`
- `KERNEL32!GetProcessHeap` at `0x18000d7f0`
- `KERNEL32!GetProcessHeap` at `0x18000d8eb`
- `KERNEL32!GetProcessHeap` at `0x18000d966`
- `KERNEL32!GetCurrentProcessId` at `0x18000d879`
- `KERNEL32!GetCurrentProcessId` at `0x18000d879`
- `KERNEL32!GetCurrentThreadId` at `0x18000d882`
- `KERNEL32!GetCurrentThreadId` at `0x18000d882`
- `KERNEL32!HeapAlloc` at `0x18000d804`
- `KERNEL32!HeapAlloc` at `0x18000d8fc`
- `KERNEL32!HeapAlloc` at `0x18000d804`
- `KERNEL32!HeapAlloc` at `0x18000d8fc`

## pseudocode

```c
_DWORD *WiaTrace_TraceWithSubCompTraceLevel(int a1, int a2, const char *a3, ...)
{
  _DWORD *result; // rax
  HANDLE ProcessHeap; // rax
  _DWORD *v7; // rsi
  DWORD CurrentThreadId; // eax
  unsigned int (*v9)(void); // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  char *v13; // rdi
  unsigned __int64 v14; // rbx
  HANDLE v15; // rax
  char *v16; // rax
  char *v17; // rbp
  __int64 v18; // r8
  unsigned __int64 v19; // rcx
  char *v20; // rax
  unsigned __int64 v21; // r9
  int v22; // eax
  char *v23; // rax
  HANDLE v24; // rax
  char *v25; // rdx
  char *v26; // rcx
  unsigned __int64 i; // rbx
  char Buffer[512]; // [rsp+30h] [rbp-238h] BYREF
  va_list ArgList; // [rsp+288h] [rbp+20h] BYREF

  va_start(ArgList, a3);
  result = 0;
  if ( (g_WiaTrace_ulFlags & 4) != 0 )
  {
    ProcessHeap = GetProcessHeap();
    result = HeapAlloc(ProcessHeap, 8u, 0x40u);
    v7 = result;
    if ( result )
    {
      memset_0(Buffer, 0, sizeof(Buffer));
      memset_0(v7, 0, 0x40u);
      if ( (unsigned int)vsnprintf(Buffer, 0x1FFu, a3, ArgList) > 0x1FE )
        Buffer[511] = 0;
      v7[13] = a1;
      v7[15] = a2;
      v7[3] = GetCurrentProcessId();
      CurrentThreadId = GetCurrentThreadId();
      v9 = WiaTrcLib::g_WiaTrc_GetIndentLevel;
      v7[4] = CurrentThreadId;
      v10 = 0;
      if ( v9 )
        v10 = ((__int64 (__fastcall *)(unsigned int (*)(void)))v9)(v9);
      v11 = -1;
      v7[14] = v10;
      v12 = -1;
      do
        ++v12;
      while ( Buffer[v12] );
      if ( !v12 )
        return v7;
      v13 = *(char **)v7;
      if ( *(_QWORD *)v7 )
      {
        do
          ++v11;
        while ( v13[v11] );
      }
      else
      {
        LODWORD(v11) = 0;
      }
      if ( (_DWORD)v12 + (_DWORD)v11 + 1 )
      {
        v14 = (unsigned int)(v12 + v11 + 1);
        v15 = GetProcessHeap();
        v16 = (char *)HeapAlloc(v15, 8u, (unsigned int)v14);
        v17 = v16;
        if ( v16 )
        {
          memset_0(v16, 0, (unsigned int)v14);
          if ( v13 )
            StringCchCopyA(v17, v14, v13);
          v18 = 2147483646;
          if ( v14 - 1 <= 0x7FFFFFFE )
          {
            v19 = v14;
            v20 = v17;
            while ( *v20 )
            {
              ++v20;
              if ( !--v19 )
              {
                v21 = 0;
                v22 = -2147024809;
                goto LABEL_29;
              }
            }
            v21 = v14 - v19;
            v22 = 0;
LABEL_29:
            if ( v22 >= 0 )
            {
              v25 = Buffer;
              v26 = &v17[v21];
              for ( i = v14 - v21; i; --i )
              {
                if ( !v18 )
                  break;
                if ( !*v25 )
                  break;
                *v26++ = *v25++;
                --v18;
              }
              v23 = v26 - 1;
              if ( i )
                v23 = v26;
              *v23 = 0;
            }
          }
          _InterlockedExchange64((volatile __int64 *)v7, (__int64)v17);
          if ( v13 )
          {
            v24 = GetProcessHeap();
            HeapFree(v24, 0, v13);
          }
        }
        return v7;
      }
      else
      {
        return v7;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d7b0  mov     [rsp+Format], r8
0x18000d7b5  mov     qword ptr [rsp+ArgList], r9
0x18000d7ba  push    rbx
0x18000d7bb  push    rdi
0x18000d7bc  sub     rsp, 258h
0x18000d7c3  mov     rax, cs:__security_cookie
0x18000d7ca  xor     rax, rsp
0x18000d7cd  mov     [rsp+268h+var_38], rax
0x18000d7d5  xor     eax, eax
0x18000d7d7  mov     ebx, edx
0x18000d7d9  test    byte ptr cs:g_WiaTrace_ulFlags, 4
0x18000d7e0  mov     edi, ecx
0x18000d7e2  jz      loc_18000D98D
0x18000d7e8  mov     [rsp+268h+var_20], rsi
0x18000d7f0  call    cs:__imp_GetProcessHeap
0x18000d7f6  mov     edx, 8; dwFlags
0x18000d7fb  mov     r8d, 40h ; '@'; dwBytes
0x18000d801  mov     rcx, rax; hHeap
0x18000d804  call    cs:__imp_HeapAlloc
0x18000d80a  mov     rsi, rax
0x18000d80d  test    rax, rax
0x18000d810  jz      loc_18000D985
0x18000d816  xor     edx, edx; Val
0x18000d818  lea     rcx, [rsp+268h+Buffer]; void *
0x18000d81d  mov     r8d, 200h; Size
0x18000d823  call    memset_0
0x18000d828  xor     edx, edx; Val
0x18000d82a  mov     r8d, 40h ; '@'; Size
0x18000d830  mov     rcx, rsi; void *
0x18000d833  call    memset_0
0x18000d838  mov     r8, [rsp+268h+Format]; Format
0x18000d840  lea     r9, [rsp+268h+ArgList]; ArgList
0x18000d848  mov     edx, 1FFh; BufferCount
0x18000d84d  mov     [rsp+268h+var_248], 0
0x18000d856  lea     rcx, [rsp+268h+Buffer]; Buffer
0x18000d85b  call    _vsnprintf
0x18000d860  test    eax, eax
0x18000d862  js      short loc_18000D86B
0x18000d864  cmp     eax, 1FFh
0x18000d869  jb      short loc_18000D873
0x18000d86b  mov     [rsp+268h+var_39], 0
0x18000d873  mov     [rsi+34h], edi
0x18000d876  mov     [rsi+3Ch], ebx
0x18000d879  call    cs:__imp_GetCurrentProcessId
0x18000d87f  mov     [rsi+0Ch], eax
0x18000d882  call    cs:__imp_GetCurrentThreadId
0x18000d888  mov     rcx, cs:?g_WiaTrc_GetIndentLevel@WiaTrcLib@@3P6AKXZEA; ulong (*WiaTrcLib::g_WiaTrc_GetIndentLevel)(void)
0x18000d88f  mov     [rsi+10h], eax
0x18000d892  xor     eax, eax
0x18000d894  test    rcx, rcx
0x18000d897  jz      short loc_18000D8A1
0x18000d899  mov     rax, rcx
0x18000d89c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8a1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d8a8  mov     [rsi+38h], eax
0x18000d8ab  mov     rax, rcx
0x18000d8ae  lea     rdx, [rsp+268h+Buffer]
0x18000d8b3  inc     rax
0x18000d8b6  cmp     byte ptr [rdx+rax], 0
0x18000d8ba  jnz     short loc_18000D8B3
0x18000d8bc  test    rax, rax
0x18000d8bf  jz      loc_18000D9E2
0x18000d8c5  mov     rdi, [rsi]
0x18000d8c8  test    rdi, rdi
0x18000d8cb  jnz     loc_18000D9E7
0x18000d8d1  xor     ecx, ecx
0x18000d8d3  lea     r8d, [rcx+1]
0x18000d8d7  add     r8d, eax
0x18000d8da  jz      loc_18000D9E2
0x18000d8e0  mov     [rsp+268h+var_18], rbp
0x18000d8e8  mov     ebx, r8d
0x18000d8eb  call    cs:__imp_GetProcessHeap
0x18000d8f1  mov     r8d, ebx; dwBytes
0x18000d8f4  mov     edx, 8; dwFlags
0x18000d8f9  mov     rcx, rax; hHeap
0x18000d8fc  call    cs:__imp_HeapAlloc
0x18000d902  mov     rbp, rax
0x18000d905  test    rax, rax
0x18000d908  jz      short loc_18000D97A
0x18000d90a  mov     r8d, ebx; Size
0x18000d90d  xor     edx, edx; Val
0x18000d90f  mov     rcx, rax; void *
0x18000d912  call    memset_0
0x18000d917  test    rdi, rdi
0x18000d91a  jnz     loc_18000D9F5
0x18000d920  lea     rax, [rbx-1]
0x18000d924  mov     r8d, 7FFFFFFEh
0x18000d92a  cmp     rax, r8
0x18000d92d  ja      short loc_18000D95E
0x18000d92f  mov     rcx, rbx
0x18000d932  mov     rax, rbp
0x18000d935  mov     r9, rbx
0x18000d938  cmp     byte ptr [rax], 0
0x18000d93b  jz      short loc_18000D9A7
0x18000d93d  inc     rax
0x18000d940  sub     rcx, 1
0x18000d944  jnz     short loc_18000D938
0x18000d946  xor     r9d, r9d
0x18000d949  mov     eax, 80070057h
0x18000d94e  jmp     short loc_18000D9AC
0x18000d950  test    rbx, rbx
0x18000d953  lea     rax, [rcx-1]
0x18000d957  cmovnz  rax, rcx
0x18000d95b  mov     byte ptr [rax], 0
0x18000d95e  xchg    rbp, [rsi]
0x18000d961  test    rdi, rdi
0x18000d964  jz      short loc_18000D97A
0x18000d966  call    cs:__imp_GetProcessHeap
0x18000d96c  mov     r8, rdi; lpMem
0x18000d96f  xor     edx, edx; dwFlags
0x18000d971  mov     rcx, rax; hHeap
0x18000d974  call    cs:__imp_HeapFree
0x18000d97a  mov     rbp, [rsp+268h+var_18]
0x18000d982  mov     rax, rsi
0x18000d985  mov     rsi, [rsp+268h+var_20]
0x18000d98d  mov     rcx, [rsp+268h+var_38]
0x18000d995  xor     rcx, rsp; StackCookie
0x18000d998  call    __security_check_cookie
0x18000d99d  add     rsp, 258h
0x18000d9a4  pop     rdi
0x18000d9a5  pop     rbx
0x18000d9a6  retn
0x18000d9a7  sub     r9, rcx
0x18000d9aa  xor     eax, eax
0x18000d9ac  test    eax, eax
0x18000d9ae  js      short loc_18000D95E
0x18000d9b0  lea     rdx, [rsp+268h+Buffer]
0x18000d9b5  lea     rcx, [r9+rbp]
0x18000d9b9  sub     rbx, r9
0x18000d9bc  jz      short loc_18000D950
0x18000d9be  xchg    ax, ax
0x18000d9c0  test    r8, r8
0x18000d9c3  jz      short loc_18000D950
0x18000d9c5  movzx   eax, byte ptr [rdx]
0x18000d9c8  test    al, al
0x18000d9ca  jz      short loc_18000D950
0x18000d9cc  mov     [rcx], al
0x18000d9ce  inc     rdx
0x18000d9d1  inc     rcx
0x18000d9d4  dec     r8
0x18000d9d7  sub     rbx, 1
0x18000d9db  jnz     short loc_18000D9C0
0x18000d9dd  jmp     loc_18000D950
0x18000d9e2  mov     rax, rsi
0x18000d9e5  jmp     short loc_18000D985
0x18000d9e7  inc     rcx
0x18000d9ea  cmp     byte ptr [rdi+rcx], 0
0x18000d9ee  jnz     short loc_18000D9E7
0x18000d9f0  jmp     loc_18000D8D3
0x18000d9f5  mov     r8, rdi; char *
0x18000d9f8  mov     rdx, rbx; unsigned __int64
0x18000d9fb  mov     rcx, rbp; char *
0x18000d9fe  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18000da03  jmp     loc_18000D920
```
