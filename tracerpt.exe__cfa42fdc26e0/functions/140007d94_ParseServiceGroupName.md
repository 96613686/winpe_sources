# ParseServiceGroupName

- ea: `0x140007d94`
- end: `0x140007ebe`
- name: `ParseServiceGroupName`
- size: `298`
- prototype: `int __fastcall(__int64, wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140008d14`

## callees

- `0x140007d94`
- `0x140009c04`
- `0x140040130`

## import_xrefs

- `msvcrt!wcstok_s` at `0x140007e29`
- `msvcrt!wcstok_s` at `0x140007e29`
- `msvcrt!_wcsicmp` at `0x140007e0a`
- `msvcrt!_wcsicmp` at `0x140007e0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007e92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007e92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007e53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007e84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007e53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007e84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007e64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007e64`

## pseudocode

```c
int __fastcall ParseServiceGroupName(__int64 a1, wchar_t *a2)
{
  __int64 v3; // rax
  bool v4; // bl
  unsigned __int16 *v6; // rdi
  unsigned __int64 v7; // r14
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  wchar_t Delimiter[4]; // [rsp+20h] [rbp-38h] BYREF
  wchar_t *Context; // [rsp+28h] [rbp-30h] BYREF
  wchar_t String1[4]; // [rsp+30h] [rbp-28h] BYREF

  wcscpy(String1, L"-k");
  v3 = a1 + 32;
  wcscpy(Delimiter, L" ");
  Context = 0;
  if ( *(_QWORD *)v3 != v3 && *(_DWORD *)(a1 + 120) )
  {
    v4 = 0;
    while ( 1 )
    {
      v3 = (__int64)wcstok_s(a2, Delimiter, &Context);
      v6 = (unsigned __int16 *)v3;
      if ( !v3 )
        break;
      if ( v4 )
      {
        v3 = -1;
        do
          ++v3;
        while ( v6[v3] );
        if ( v3 )
        {
          v7 = v3 + 1;
          v8 = 2 * (v3 + 1);
          ProcessHeap = GetProcessHeap();
          v3 = (__int64)HeapAlloc(ProcessHeap, 8u, v8);
          v10 = (void *)v3;
          if ( v3 )
          {
            LODWORD(v3) = StringCchCopyW((unsigned __int16 *)v3, v7, v6);
            if ( (int)v3 >= 0 )
            {
              *(_QWORD *)(a1 + 112) = v10;
            }
            else
            {
              v11 = GetProcessHeap();
              LODWORD(v3) = HeapFree(v11, 0, v10);
            }
          }
        }
        return v3;
      }
      v4 = _wcsicmp(String1, (const wchar_t *)v3) == 0;
      a2 = 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140007d94  mov     [rsp+arg_10], rbx
0x140007d99  mov     [rsp+arg_18], rbp
0x140007d9e  push    rsi
0x140007d9f  push    rdi
0x140007da0  push    r14
0x140007da2  sub     rsp, 40h
0x140007da6  mov     rax, cs:__security_cookie
0x140007dad  xor     rax, rsp
0x140007db0  mov     [rsp+58h+var_20], rax
0x140007db5  mov     eax, dword ptr cs:aK; "-k"
0x140007dbb  xor     ebp, ebp
0x140007dbd  mov     dword ptr [rsp+58h+String1], eax
0x140007dc1  mov     r9, rdx
0x140007dc4  movzx   eax, word ptr cs:aK+4; ""
0x140007dcb  mov     rsi, rcx
0x140007dce  mov     [rsp+58h+var_24], ax
0x140007dd3  lea     rax, [rcx+20h]
0x140007dd7  mov     dword ptr [rsp+58h+Delimiter], 20h ; ' '
0x140007ddf  mov     [rsp+58h+Context], rbp
0x140007de4  cmp     [rax], rax
0x140007de7  jz      loc_140007E9E
0x140007ded  cmp     [rcx+78h], ebp
0x140007df0  jz      loc_140007E9E
0x140007df6  mov     bl, bpl
0x140007df9  mov     rcx, rdx
0x140007dfc  jmp     short loc_140007E1F
0x140007dfe  test    bl, bl
0x140007e00  jnz     short loc_140007E39
0x140007e02  mov     rdx, rdi; String2
0x140007e05  lea     rcx, [rsp+58h+String1]; String1
0x140007e0a  call    cs:__imp__wcsicmp
0x140007e10  mov     ecx, 1
0x140007e15  movzx   ebx, bl
0x140007e18  test    eax, eax
0x140007e1a  cmovz   ebx, ecx
0x140007e1d  xor     ecx, ecx; String
0x140007e1f  lea     r8, [rsp+58h+Context]; Context
0x140007e24  lea     rdx, [rsp+58h+Delimiter]; Delimiter
0x140007e29  call    cs:__imp_wcstok_s
0x140007e2f  mov     rdi, rax
0x140007e32  test    rax, rax
0x140007e35  jnz     short loc_140007DFE
0x140007e37  jmp     short loc_140007E9E
0x140007e39  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007e3d  inc     rax
0x140007e40  cmp     [rdi+rax*2], bp
0x140007e44  jnz     short loc_140007E3D
0x140007e46  test    rax, rax
0x140007e49  jz      short loc_140007E9E
0x140007e4b  lea     r14, [rax+1]
0x140007e4f  lea     rbx, [r14+r14]
0x140007e53  call    cs:__imp_GetProcessHeap
0x140007e59  mov     r8, rbx; dwBytes
0x140007e5c  mov     edx, 8; dwFlags
0x140007e61  mov     rcx, rax; hHeap
0x140007e64  call    cs:__imp_HeapAlloc
0x140007e6a  mov     rbx, rax
0x140007e6d  test    rax, rax
0x140007e70  jz      short loc_140007E9E
0x140007e72  mov     r8, rdi; unsigned __int16 *
0x140007e75  mov     rdx, r14; unsigned __int64
0x140007e78  mov     rcx, rax; unsigned __int16 *
0x140007e7b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140007e80  test    eax, eax
0x140007e82  jns     short loc_140007E9A
0x140007e84  call    cs:__imp_GetProcessHeap
0x140007e8a  mov     r8, rbx; lpMem
0x140007e8d  xor     edx, edx; dwFlags
0x140007e8f  mov     rcx, rax; hHeap
0x140007e92  call    cs:__imp_HeapFree
0x140007e98  jmp     short loc_140007E9E
0x140007e9a  mov     [rsi+70h], rbx
0x140007e9e  mov     rcx, [rsp+58h+var_20]
0x140007ea3  xor     rcx, rsp; StackCookie
0x140007ea6  call    __security_check_cookie
0x140007eab  mov     rbx, [rsp+58h+arg_10]
0x140007eb0  mov     rbp, [rsp+58h+arg_18]
0x140007eb5  add     rsp, 40h
0x140007eb9  pop     r14
0x140007ebb  pop     rdi
0x140007ebc  pop     rsi
0x140007ebd  retn
```
