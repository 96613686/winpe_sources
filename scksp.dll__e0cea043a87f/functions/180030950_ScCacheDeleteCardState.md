# ScCacheDeleteCardState

- ea: `0x180030950`
- end: `0x180030a7b`
- name: `ScCacheDeleteCardState`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180034aa0`

## callees

- `0x18000a408`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x18002ce34`
- `0x180030950`
- `0x180037120`
- `0x180037730`
- `0x18003ae44`
- `0x18003aec8`

## pseudocode

```c
__int64 __fastcall ScCacheDeleteCardState(__int64 a1, struct _RTL_CRITICAL_SECTION *a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // eax
  __int64 v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // rsi
  __int64 v12; // rcx
  int v14; // [rsp+20h] [rbp-78h]
  int v15; // [rsp+28h] [rbp-70h]
  __int64 v16; // [rsp+40h] [rbp-58h] BYREF
  __int64 v17[10]; // [rsp+48h] [rbp-50h] BYREF

  v17[0] = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids, WPP_pszIndent);
  }
  CspEnterCriticalSection(a1);
  v8 = ScCacheRead(a2, a3, 0, a4, v14, v15, v17, &v16);
  v9 = v17[0];
  v10 = v8;
  if ( !v8 )
  {
    v11 = *(_QWORD *)v17[0];
    v10 = ScCacheDeleteItem(a2);
    if ( !v10 )
      CardStateReleaseRef(v11, 0);
  }
  if ( v9 )
    CspFreeH(v9);
  CspLeaveCriticalSection(a1);
  WppTraceIndent(v12, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
      (_DWORD)WPP_pszIndent,
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x180030950  push    rbx
0x180030952  push    rbp
0x180030953  push    rsi
0x180030954  push    rdi
0x180030955  push    r12
0x180030957  push    r13
0x180030959  push    r14
0x18003095b  push    r15
0x18003095d  sub     rsp, 58h
0x180030961  mov     r12, rdx
0x180030964  mov     [rsp+98h+var_50], 0
0x18003096d  xor     edx, edx
0x18003096f  mov     r14, r9
0x180030972  mov     r15, r8
0x180030975  mov     rbp, rcx
0x180030978  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003097d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030984  lea     r13, WPP_GLOBAL_Control
0x18003098b  cmp     rcx, r13
0x18003098e  jz      short loc_1800309B8
0x180030990  test    byte ptr [rcx+1Ch], 2
0x180030994  jz      short loc_1800309B8
0x180030996  cmp     byte ptr [rcx+19h], 5
0x18003099a  jb      short loc_1800309B8
0x18003099c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800309a3  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x1800309aa  mov     rcx, [rcx+10h]
0x1800309ae  mov     edx, 23h ; '#'
0x1800309b3  call    WPP_SF_s
0x1800309b8  mov     rcx, rbp
0x1800309bb  call    CspEnterCriticalSection
0x1800309c0  lea     rax, [rsp+98h+var_58]
0x1800309c5  mov     r9, r14
0x1800309c8  mov     [rsp+98h+var_60], rax; __int64
0x1800309cd  xor     r8d, r8d
0x1800309d0  lea     rax, [rsp+98h+var_50]
0x1800309d5  mov     rdx, r15
0x1800309d8  mov     rcx, r12; lpCriticalSection
0x1800309db  mov     [rsp+98h+var_68], rax; __int64
0x1800309e0  call    ScCacheRead
0x1800309e5  mov     rdi, [rsp+98h+var_50]
0x1800309ea  mov     ebx, eax
0x1800309ec  test    eax, eax
0x1800309ee  jnz     short loc_180030A11
0x1800309f0  mov     rsi, [rdi]
0x1800309f3  mov     r8, r14
0x1800309f6  mov     rdx, r15
0x1800309f9  mov     rcx, r12; lpCriticalSection
0x1800309fc  call    ScCacheDeleteItem
0x180030a01  mov     ebx, eax
0x180030a03  test    eax, eax
0x180030a05  jnz     short loc_180030A11
0x180030a07  xor     edx, edx
0x180030a09  mov     rcx, rsi
0x180030a0c  call    CardStateReleaseRef
0x180030a11  test    rdi, rdi
0x180030a14  jz      short loc_180030A1E
0x180030a16  mov     rcx, rdi
0x180030a19  call    CspFreeH
0x180030a1e  mov     rcx, rbp
0x180030a21  call    CspLeaveCriticalSection
0x180030a26  mov     edx, 1
0x180030a2b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180030a30  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a37  cmp     rcx, r13
0x180030a3a  jz      short loc_180030A68
0x180030a3c  test    byte ptr [rcx+1Ch], 2
0x180030a40  jz      short loc_180030A68
0x180030a42  cmp     byte ptr [rcx+19h], 5
0x180030a46  jb      short loc_180030A68
0x180030a48  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180030a4f  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180030a56  mov     rcx, [rcx+10h]
0x180030a5a  mov     edx, 24h ; '$'
0x180030a5f  mov     [rsp+98h+var_78], ebx
0x180030a63  call    WPP_SF_sd
0x180030a68  mov     eax, ebx
0x180030a6a  add     rsp, 58h
0x180030a6e  pop     r15
0x180030a70  pop     r14
0x180030a72  pop     r13
0x180030a74  pop     r12
0x180030a76  pop     rdi
0x180030a77  pop     rsi
0x180030a78  pop     rbp
0x180030a79  pop     rbx
0x180030a7a  retn
```
