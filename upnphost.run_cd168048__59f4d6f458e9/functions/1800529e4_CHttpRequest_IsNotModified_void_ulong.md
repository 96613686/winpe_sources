# CHttpRequest::IsNotModified(void *,ulong)

- ea: `0x1800529e4`
- end: `0x180052b0b`
- name: `?IsNotModified@CHttpRequest@@AEAAHPEAXK@Z`
- size: `295`
- prototype: `int(CHttpRequest *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800175c0`

## callees

- `0x1800480c0`
- `0x1800529e4`
- `0x180052eac`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180052a25`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180052a25`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180052a89`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180052a89`

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
0x1800529e4  mov     [rsp+arg_8], rbx
0x1800529e9  mov     [rsp+arg_10], rbp
0x1800529ee  push    rsi
0x1800529ef  push    rdi
0x1800529f0  push    r14
0x1800529f2  sub     rsp, 50h
0x1800529f6  lea     r14, [rcx+60h]
0x1800529fa  mov     ebp, r8d
0x1800529fd  cmp     dword ptr [r14], 0
0x180052a01  mov     rsi, rdx
0x180052a04  mov     rdi, rcx
0x180052a07  jnz     short loc_180052A0F
0x180052a09  cmp     dword ptr [rcx+64h], 0
0x180052a0d  jz      short loc_180052A69
0x180052a0f  lea     r9, [rsp+68h+LastWriteTime]; lpLastWriteTime
0x180052a14  mov     qword ptr [rsp+68h+LastWriteTime.dwLowDateTime], 0
0x180052a1d  xor     r8d, r8d; lpLastAccessTime
0x180052a20  xor     edx, edx; lpCreationTime
0x180052a22  mov     rcx, rsi; hFile
0x180052a25  call    cs:__imp_GetFileTime
0x180052a2c  nop     dword ptr [rax+rax+00h]
0x180052a31  test    eax, eax
0x180052a33  jnz     short loc_180052A81
0x180052a35  mov     rcx, cs:WPP_GLOBAL_Control
0x180052a3c  lea     rax, WPP_GLOBAL_Control
0x180052a43  cmp     rcx, rax
0x180052a46  jz      short loc_180052A69
0x180052a48  test    dword ptr [rcx+1Ch], 1000h
0x180052a4f  jz      short loc_180052A69
0x180052a51  mov     rcx, [rcx+10h]
0x180052a55  lea     r8, WPP_17616c072cb339da1efa148f0bfe4571_Traceguids
0x180052a5c  mov     edx, 12h
0x180052a61  mov     r9, rsi
0x180052a64  call    WPP_SF_q
0x180052a69  xor     eax, eax
0x180052a6b  lea     r11, [rsp+68h+var_18]
0x180052a70  mov     rbx, [r11+28h]
0x180052a74  mov     rbp, [r11+30h]
0x180052a78  mov     rsp, r11
0x180052a7b  pop     r14
0x180052a7d  pop     rdi
0x180052a7e  pop     rsi
0x180052a7f  retn
0x180052a81  lea     rdx, [rsp+68h+LastWriteTime]; lpFileTime2
0x180052a86  mov     rcx, r14; lpFileTime1
0x180052a89  call    cs:__imp_CompareFileTime
0x180052a90  nop     dword ptr [rax+rax+00h]
0x180052a95  mov     esi, eax
0x180052a97  mov     rcx, cs:WPP_GLOBAL_Control
0x180052a9e  lea     rax, WPP_GLOBAL_Control
0x180052aa5  cmp     rcx, rax
0x180052aa8  jz      short loc_180052AE6
0x180052aaa  test    dword ptr [rcx+1Ch], 1000h
0x180052ab1  jz      short loc_180052AE6
0x180052ab3  mov     eax, [rdi+68h]
0x180052ab6  mov     r9d, [rdi+64h]
0x180052aba  mov     rcx, [rcx+10h]
0x180052abe  mov     [rsp+68h+var_20], esi
0x180052ac2  mov     [rsp+68h+var_28], ebp
0x180052ac6  mov     [rsp+68h+var_30], eax
0x180052aca  mov     eax, [rsp+68h+LastWriteTime.dwLowDateTime]
0x180052ace  mov     [rsp+68h+var_38], eax
0x180052ad2  mov     eax, [rsp+68h+LastWriteTime.dwHighDateTime]
0x180052ad6  mov     [rsp+68h+var_40], eax
0x180052ada  mov     eax, [r14]
0x180052add  mov     [rsp+68h+var_48], eax
0x180052ae1  call    WPP_SF_DDDDddd
0x180052ae6  test    esi, esi
0x180052ae8  js      loc_180052A69
0x180052aee  cmp     dword ptr [rdi+68h], 0
0x180052af2  jz      short loc_180052B01
0x180052af4  xor     eax, eax
0x180052af6  cmp     ebp, [rdi+68h]
0x180052af9  setz    al
0x180052afc  jmp     loc_180052A6B
0x180052b01  mov     eax, 1
0x180052b06  jmp     loc_180052A6B
```
