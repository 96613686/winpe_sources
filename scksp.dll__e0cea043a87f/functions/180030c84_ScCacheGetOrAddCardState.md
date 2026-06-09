# ScCacheGetOrAddCardState

- ea: `0x180030c84`
- end: `0x180030e74`
- name: `ScCacheGetOrAddCardState`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180031a94`

## callees

- `0x18000a408`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x180030c84`
- `0x180037120`
- `0x180037730`
- `0x180037a4c`
- `0x18003ae44`
- `0x18003aec8`

## pseudocode

```c
__int64 __fastcall ScCacheGetOrAddCardState(
        __int64 a1,
        __int64 a2,
        struct _RTL_CRITICAL_SECTION *a3,
        char *a4,
        __int64 a5,
        _QWORD *a6)
{
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdi
  unsigned int v12; // ebx
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rcx
  int v17; // [rsp+20h] [rbp-48h]
  int v18; // [rsp+28h] [rbp-40h]
  __int64 v19; // [rsp+40h] [rbp-28h] BYREF
  __int64 v20; // [rsp+48h] [rbp-20h] BYREF
  __int64 Src; // [rsp+78h] [rbp+10h] BYREF

  Src = a2;
  v20 = 0;
  LODWORD(v19) = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids, WPP_pszIndent);
  }
  CspEnterCriticalSection(a1);
  v9 = ScCacheRead(a3, (__int64)a4, 0, a5, v17, v18, &v20, &v19);
  v11 = v20;
  v12 = v9;
  if ( v9 )
  {
    if ( v9 + 2146434960 <= 1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(Src + 692));
      v14 = ScCacheWrite(a3, a4, 0, a5, 0, 0, &Src, 8u);
      if ( v14 )
        v12 = v14;
    }
  }
  else if ( (_DWORD)v19 == 8 )
  {
    v13 = *(_QWORD *)v20;
    *a6 = *(_QWORD *)v20;
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 692));
  }
  else
  {
    WppTraceIndent(v10, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids, WPP_pszIndent);
    }
    ScCacheDeleteItem(a3);
    v12 = -2146435041;
  }
  if ( v11 )
    CspFreeH(v11);
  CspLeaveCriticalSection(a1);
  WppTraceIndent(v15, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
      (_DWORD)WPP_pszIndent,
      v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180030c84  mov     rax, rsp
0x180030c87  mov     [rax+8], rbx
0x180030c8b  mov     [rax+18h], rbp
0x180030c8f  mov     [rax+10h], rdx
0x180030c93  push    rsi
0x180030c94  push    rdi
0x180030c95  push    r15
0x180030c97  sub     rsp, 50h
0x180030c9b  xor     edx, edx
0x180030c9d  mov     qword ptr [rax-20h], 0
0x180030ca5  mov     rsi, r9
0x180030ca8  mov     dword ptr [rax-28h], 0
0x180030caf  mov     rbp, r8
0x180030cb2  mov     r15, rcx
0x180030cb5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180030cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180030cc1  lea     rax, WPP_GLOBAL_Control
0x180030cc8  cmp     rcx, rax
0x180030ccb  jz      short loc_180030CF5
0x180030ccd  test    byte ptr [rcx+1Ch], 2
0x180030cd1  jz      short loc_180030CF5
0x180030cd3  cmp     byte ptr [rcx+19h], 5
0x180030cd7  jb      short loc_180030CF5
0x180030cd9  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180030ce0  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180030ce7  mov     rcx, [rcx+10h]
0x180030ceb  mov     edx, 1Eh
0x180030cf0  call    WPP_SF_s
0x180030cf5  mov     rcx, r15
0x180030cf8  call    CspEnterCriticalSection
0x180030cfd  mov     r9, [rsp+68h+arg_20]
0x180030d05  lea     rax, [rsp+68h+var_28]
0x180030d0a  mov     [rsp+68h+var_30], rax; __int64
0x180030d0f  xor     r8d, r8d
0x180030d12  lea     rax, [rsp+68h+var_20]
0x180030d17  mov     rdx, rsi
0x180030d1a  mov     rcx, rbp; lpCriticalSection
0x180030d1d  mov     [rsp+68h+Src], rax; __int64
0x180030d22  call    ScCacheRead
0x180030d27  mov     rdi, [rsp+68h+var_20]
0x180030d2c  mov     ebx, eax
0x180030d2e  test    eax, eax
0x180030d30  jnz     short loc_180030DAB
0x180030d32  cmp     dword ptr [rsp+68h+var_28], 8
0x180030d37  jz      short loc_180030D94
0x180030d39  lea     edx, [rax+2]
0x180030d3c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180030d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d48  lea     rax, WPP_GLOBAL_Control
0x180030d4f  cmp     rcx, rax
0x180030d52  jz      short loc_180030D7A
0x180030d54  test    byte ptr [rcx+1Ch], 1
0x180030d58  jz      short loc_180030D7A
0x180030d5a  cmp     byte ptr [rcx+19h], 2
0x180030d5e  jb      short loc_180030D7A
0x180030d60  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180030d67  lea     edx, [rbx+1Fh]
0x180030d6a  mov     rcx, [rcx+10h]
0x180030d6e  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180030d75  call    WPP_SF_s
0x180030d7a  mov     r8, [rsp+68h+arg_20]
0x180030d82  mov     rdx, rsi
0x180030d85  mov     rcx, rbp; lpCriticalSection
0x180030d88  call    ScCacheDeleteItem
0x180030d8d  mov     ebx, 8010001Fh
0x180030d92  jmp     short loc_180030DFF
0x180030d94  mov     rax, [rsp+68h+arg_28]
0x180030d9c  mov     rcx, [rdi]
0x180030d9f  mov     [rax], rcx
0x180030da2  lock inc dword ptr [rcx+2B4h]
0x180030da9  jmp     short loc_180030DFF
0x180030dab  add     eax, 7FEFFF90h
0x180030db0  cmp     eax, 1
0x180030db3  ja      short loc_180030DFF
0x180030db5  mov     rax, [rsp+68h+arg_8]
0x180030dba  lock inc dword ptr [rax+2B4h]
0x180030dc1  mov     r9, [rsp+68h+arg_20]
0x180030dc9  lea     rax, [rsp+68h+arg_8]
0x180030dce  mov     dword ptr [rsp+68h+var_30], 8; int
0x180030dd6  xor     r8d, r8d
0x180030dd9  mov     [rsp+68h+Src], rax; Src
0x180030dde  mov     rdx, rsi
0x180030de1  mov     qword ptr [rsp+68h+var_40], 0; int
0x180030dea  mov     rcx, rbp; lpCriticalSection
0x180030ded  mov     [rsp+68h+var_48], 0; int
0x180030df5  call    ScCacheWrite
0x180030dfa  test    eax, eax
0x180030dfc  cmovnz  ebx, eax
0x180030dff  test    rdi, rdi
0x180030e02  jz      short loc_180030E0C
0x180030e04  mov     rcx, rdi
0x180030e07  call    CspFreeH
0x180030e0c  mov     rcx, r15
0x180030e0f  call    CspLeaveCriticalSection
0x180030e14  mov     edx, 1
0x180030e19  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180030e1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e25  lea     rax, WPP_GLOBAL_Control
0x180030e2c  cmp     rcx, rax
0x180030e2f  jz      short loc_180030E5D
0x180030e31  test    byte ptr [rcx+1Ch], 2
0x180030e35  jz      short loc_180030E5D
0x180030e37  cmp     byte ptr [rcx+19h], 5
0x180030e3b  jb      short loc_180030E5D
0x180030e3d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180030e44  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180030e4b  mov     rcx, [rcx+10h]
0x180030e4f  mov     edx, 20h ; ' '
0x180030e54  mov     [rsp+68h+var_48], ebx
0x180030e58  call    WPP_SF_sd
0x180030e5d  lea     r11, [rsp+68h+var_18]
0x180030e62  mov     eax, ebx
0x180030e64  mov     rbx, [r11+20h]
0x180030e68  mov     rbp, [r11+30h]
0x180030e6c  mov     rsp, r11
0x180030e6f  pop     r15
0x180030e71  pop     rdi
0x180030e72  pop     rsi
0x180030e73  retn
```
