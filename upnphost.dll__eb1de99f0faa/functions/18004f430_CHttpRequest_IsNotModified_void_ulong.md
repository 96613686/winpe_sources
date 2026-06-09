# CHttpRequest::IsNotModified(void *,ulong)

- ea: `0x18004f430`
- end: `0x18004f546`
- name: `?IsNotModified@CHttpRequest@@AEAAHPEAXK@Z`
- size: `278`
- prototype: `int(CHttpRequest *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002b40`

## callees

- `0x1800454d0`
- `0x18004f430`
- `0x18004f8c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18004f471`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18004f471`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004f4ce`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004f4ce`

## pseudocode

```c
_BOOL8 __fastcall CHttpRequest::IsNotModified(CHttpRequest *this, void *a2, int a3)
{
  const FILETIME *v3; // r14
  __int64 v8; // rdx
  LONG v9; // esi
  __int64 v10; // r8
  struct _FILETIME LastWriteTime; // [rsp+70h] [rbp+8h] BYREF

  v3 = (const FILETIME *)((char *)this + 96);
  if ( !*((_QWORD *)this + 12) )
    return 0;
  LastWriteTime = 0;
  if ( !GetFileTime(a2, 0, 0, &LastWriteTime) )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_17616c072cb339da1efa148f0bfe4571_Traceguids, a2);
    }
    return 0;
  }
  v9 = CompareFileTime(v3, &LastWriteTime);
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_DDDDddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v10,
      *((unsigned int *)this + 25),
      v3->dwLowDateTime,
      LastWriteTime.dwHighDateTime,
      LastWriteTime.dwLowDateTime,
      *((_DWORD *)this + 26),
      a3,
      v9);
  if ( v9 < 0 )
    return 0;
  return !*((_DWORD *)this + 26) || a3 == *((_DWORD *)this + 26);
}

```

## disassembly

```asm
0x18004f430  mov     [rsp+arg_8], rbx
0x18004f435  mov     [rsp+arg_10], rbp
0x18004f43a  push    rsi
0x18004f43b  push    rdi
0x18004f43c  push    r14
0x18004f43e  sub     rsp, 50h
0x18004f442  lea     r14, [rcx+60h]
0x18004f446  mov     ebp, r8d
0x18004f449  cmp     dword ptr [r14], 0
0x18004f44d  mov     rsi, rdx
0x18004f450  mov     rdi, rcx
0x18004f453  jnz     short loc_18004F45B
0x18004f455  cmp     dword ptr [rcx+64h], 0
0x18004f459  jz      short loc_18004F4AF
0x18004f45b  lea     r9, [rsp+68h+LastWriteTime]; lpLastWriteTime
0x18004f460  mov     qword ptr [rsp+68h+LastWriteTime.dwLowDateTime], 0
0x18004f469  xor     r8d, r8d; lpLastAccessTime
0x18004f46c  xor     edx, edx; lpCreationTime
0x18004f46e  mov     rcx, rsi; hFile
0x18004f471  call    cs:__imp_GetFileTime
0x18004f477  test    eax, eax
0x18004f479  jnz     short loc_18004F4C6
0x18004f47b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f482  lea     rax, WPP_GLOBAL_Control
0x18004f489  cmp     rcx, rax
0x18004f48c  jz      short loc_18004F4AF
0x18004f48e  test    dword ptr [rcx+1Ch], 1000h
0x18004f495  jz      short loc_18004F4AF
0x18004f497  mov     rcx, [rcx+10h]
0x18004f49b  lea     r8, WPP_17616c072cb339da1efa148f0bfe4571_Traceguids
0x18004f4a2  mov     edx, 12h
0x18004f4a7  mov     r9, rsi
0x18004f4aa  call    WPP_SF_q
0x18004f4af  xor     eax, eax
0x18004f4b1  lea     r11, [rsp+68h+var_18]
0x18004f4b6  mov     rbx, [r11+28h]
0x18004f4ba  mov     rbp, [r11+30h]
0x18004f4be  mov     rsp, r11
0x18004f4c1  pop     r14
0x18004f4c3  pop     rdi
0x18004f4c4  pop     rsi
0x18004f4c5  retn
0x18004f4c6  lea     rdx, [rsp+68h+LastWriteTime]; lpFileTime2
0x18004f4cb  mov     rcx, r14; lpFileTime1
0x18004f4ce  call    cs:__imp_CompareFileTime
0x18004f4d4  mov     esi, eax
0x18004f4d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f4dd  lea     rax, WPP_GLOBAL_Control
0x18004f4e4  cmp     rcx, rax
0x18004f4e7  jz      short loc_18004F525
0x18004f4e9  test    dword ptr [rcx+1Ch], 1000h
0x18004f4f0  jz      short loc_18004F525
0x18004f4f2  mov     eax, [rdi+68h]
0x18004f4f5  mov     r9d, [rdi+64h]
0x18004f4f9  mov     rcx, [rcx+10h]
0x18004f4fd  mov     [rsp+68h+var_20], esi
0x18004f501  mov     [rsp+68h+var_28], ebp
0x18004f505  mov     [rsp+68h+var_30], eax
0x18004f509  mov     eax, [rsp+68h+LastWriteTime.dwLowDateTime]
0x18004f50d  mov     [rsp+68h+var_38], eax
0x18004f511  mov     eax, [rsp+68h+LastWriteTime.dwHighDateTime]
0x18004f515  mov     [rsp+68h+var_40], eax
0x18004f519  mov     eax, [r14]
0x18004f51c  mov     [rsp+68h+var_48], eax
0x18004f520  call    WPP_SF_DDDDddd
0x18004f525  test    esi, esi
0x18004f527  js      short loc_18004F4AF
0x18004f529  cmp     dword ptr [rdi+68h], 0
0x18004f52d  jz      short loc_18004F53C
0x18004f52f  xor     eax, eax
0x18004f531  cmp     ebp, [rdi+68h]
0x18004f534  setz    al
0x18004f537  jmp     loc_18004F4B1
0x18004f53c  mov     eax, 1
0x18004f541  jmp     loc_18004F4B1
```
