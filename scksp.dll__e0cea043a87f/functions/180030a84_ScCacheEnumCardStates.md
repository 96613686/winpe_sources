# ScCacheEnumCardStates

- ea: `0x180030a84`
- end: `0x180030b9f`
- name: `ScCacheEnumCardStates`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180034aa0`
- `0x180035d6c`

## callees

- `0x18000a408`
- `0x180011fd8`
- `0x180013734`
- `0x180030a84`
- `0x180037258`
- `0x18003ae44`
- `0x18003aec8`

## pseudocode

```c
__int64 __fastcall ScCacheEnumCardStates(__int64 a1, __int64 a2, _QWORD *a3, unsigned int *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // ebx
  unsigned int v11; // r8d
  unsigned int v12; // r9d
  __int64 i; // r10
  __int64 v14; // rcx
  unsigned int v16; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v17[6]; // [rsp+38h] [rbp-30h] BYREF

  v17[0] = 0;
  v16 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids, WPP_pszIndent);
  }
  CspEnterCriticalSection(a1);
  v10 = ScCacheEnumItems(a2, v8, v9, v17, &v16);
  if ( !v10 )
  {
    v11 = v16;
    v12 = 0;
    for ( i = v17[0]; v12 < v11; ++v12 )
      _InterlockedIncrement((volatile signed __int32 *)(**(_QWORD **)(i + 16LL * v12 + 8) + 692LL));
    *a3 = i;
    *a4 = v11;
  }
  CspLeaveCriticalSection(a1);
  WppTraceIndent(v14, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
      (_DWORD)WPP_pszIndent,
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x180030a84  push    rbx
0x180030a86  push    rbp
0x180030a87  push    rsi
0x180030a88  push    rdi
0x180030a89  push    r14
0x180030a8b  sub     rsp, 40h
0x180030a8f  mov     rbx, rdx
0x180030a92  mov     [rsp+68h+var_30], 0
0x180030a9b  xor     edx, edx
0x180030a9d  mov     [rsp+68h+var_38], 0
0x180030aa5  mov     rsi, r9
0x180030aa8  mov     r14, r8
0x180030aab  mov     rdi, rcx
0x180030aae  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180030ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x180030aba  lea     rbp, WPP_GLOBAL_Control
0x180030ac1  cmp     rcx, rbp
0x180030ac4  jz      short loc_180030AEE
0x180030ac6  test    byte ptr [rcx+1Ch], 2
0x180030aca  jz      short loc_180030AEE
0x180030acc  cmp     byte ptr [rcx+19h], 5
0x180030ad0  jb      short loc_180030AEE
0x180030ad2  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180030ad9  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180030ae0  mov     rcx, [rcx+10h]
0x180030ae4  mov     edx, 21h ; '!'
0x180030ae9  call    WPP_SF_s
0x180030aee  mov     rcx, rdi
0x180030af1  call    CspEnterCriticalSection
0x180030af6  lea     rax, [rsp+68h+var_38]
0x180030afb  mov     rcx, rbx
0x180030afe  lea     r9, [rsp+68h+var_30]
0x180030b03  mov     [rsp+68h+var_48], rax
0x180030b08  call    ScCacheEnumItems
0x180030b0d  mov     ebx, eax
0x180030b0f  test    eax, eax
0x180030b11  jnz     short loc_180030B48
0x180030b13  mov     r8d, [rsp+68h+var_38]
0x180030b18  xor     r9d, r9d
0x180030b1b  mov     r10, [rsp+68h+var_30]
0x180030b20  test    r8d, r8d
0x180030b23  jz      short loc_180030B42
0x180030b25  mov     eax, r9d
0x180030b28  add     rax, rax
0x180030b2b  mov     rax, [r10+rax*8+8]
0x180030b30  mov     rcx, [rax]
0x180030b33  lock inc dword ptr [rcx+2B4h]
0x180030b3a  inc     r9d
0x180030b3d  cmp     r9d, r8d
0x180030b40  jb      short loc_180030B25
0x180030b42  mov     [r14], r10
0x180030b45  mov     [rsi], r8d
0x180030b48  mov     rcx, rdi
0x180030b4b  call    CspLeaveCriticalSection
0x180030b50  mov     edx, 1
0x180030b55  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180030b5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b61  cmp     rcx, rbp
0x180030b64  jz      short loc_180030B92
0x180030b66  test    byte ptr [rcx+1Ch], 2
0x180030b6a  jz      short loc_180030B92
0x180030b6c  cmp     byte ptr [rcx+19h], 5
0x180030b70  jb      short loc_180030B92
0x180030b72  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180030b79  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180030b80  mov     rcx, [rcx+10h]
0x180030b84  mov     edx, 22h ; '"'
0x180030b89  mov     dword ptr [rsp+68h+var_48], ebx
0x180030b8d  call    WPP_SF_sd
0x180030b92  mov     eax, ebx
0x180030b94  add     rsp, 40h
0x180030b98  pop     r14
0x180030b9a  pop     rdi
0x180030b9b  pop     rsi
0x180030b9c  pop     rbp
0x180030b9d  pop     rbx
0x180030b9e  retn
```
