# AddCachedCardData

- ea: `0x18002fb68`
- end: `0x18002fc84`
- name: `AddCachedCardData`
- size: `284`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned int, unsigned int, void *Src, unsigned int Size, int)`
- caller_count: `6`
- callee_count: `10`
- tags: ``

## callers

- `0x18002c67c`
- `0x18002c80c`
- `0x18002c99c`
- `0x18002d7f0`
- `0x18002de34`
- `0x18002e3bc`

## callees

- `0x180009e76`
- `0x180009e82`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x180013c94`
- `0x18002b140`
- `0x18002fb68`
- `0x18002fc8c`
- `0x18003c240`

## pseudocode

```c
__int64 __fastcall AddCachedCardData(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        void *Src,
        unsigned int Size,
        int a7)
{
  __int64 v11; // rcx
  _DWORD *v12; // rbx
  unsigned int v13; // edi
  __int64 v15; // [rsp+20h] [rbp-288h] BYREF
  unsigned __int64 v16; // [rsp+28h] [rbp-280h]
  _BYTE v17[4]; // [rsp+30h] [rbp-278h] BYREF
  unsigned __int16 v18[278]; // [rsp+34h] [rbp-274h] BYREF

  memset_0(v17, 0, 0x228u);
  v16 = __PAIR64__(a4, a3);
  v15 = a1;
  StringCbCopyW(v18, 0x208u, a2);
  v12 = MIDL_user_allocate(Size + 16LL);
  if ( v12 )
  {
    v12[2] = a7;
    v12[3] = Size;
    memcpy_0(v12 + 4, Src, Size);
    v13 = CspAddCardCacheItem((struct _CARD_CACHE_QUERY_INFO *)&v15, v12);
    CspFreeH(v12);
  }
  else
  {
    WppTraceIndent(v11, 2);
    v13 = 8;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
        WPP_pszIndent,
        v15,
        v16);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x18002fb68  push    rbx
0x18002fb6a  push    rbp
0x18002fb6b  push    rsi
0x18002fb6c  push    rdi
0x18002fb6d  push    r14
0x18002fb6f  push    r15
0x18002fb71  sub     rsp, 278h
0x18002fb78  mov     rax, cs:__security_cookie
0x18002fb7f  xor     rax, rsp
0x18002fb82  mov     [rsp+2A8h+var_48], rax
0x18002fb8a  mov     r15, [rsp+2A8h+Src]
0x18002fb92  mov     edi, r8d
0x18002fb95  mov     r14d, dword ptr [rsp+2A8h+Size]
0x18002fb9d  mov     rsi, rdx
0x18002fba0  mov     rbx, rcx
0x18002fba3  xor     edx, edx; Val
0x18002fba5  mov     r8d, 228h; Size
0x18002fbab  lea     rcx, [rsp+2A8h+var_278]; void *
0x18002fbb0  mov     ebp, r9d
0x18002fbb3  call    memset_0
0x18002fbb8  mov     r8, rsi; unsigned __int16 *
0x18002fbbb  mov     [rsp+2A8h+var_280], edi
0x18002fbbf  mov     edx, 208h; unsigned __int64
0x18002fbc4  mov     [rsp+2A8h+var_27C], ebp
0x18002fbc8  lea     rcx, [rsp+2A8h+var_274]; unsigned __int16 *
0x18002fbcd  mov     [rsp+2A8h+var_288], rbx
0x18002fbd2  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fbd7  lea     rcx, [r14+10h]; size
0x18002fbdb  call    MIDL_user_allocate
0x18002fbe0  mov     rbx, rax
0x18002fbe3  test    rax, rax
0x18002fbe6  jnz     short loc_18002FC2E
0x18002fbe8  lea     edx, [rax+2]
0x18002fbeb  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002fbf0  lea     edi, [rbx+8]
0x18002fbf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbfa  lea     rax, WPP_GLOBAL_Control
0x18002fc01  cmp     rcx, rax
0x18002fc04  jz      short loc_18002FC62
0x18002fc06  test    byte ptr [rcx+1Ch], 1
0x18002fc0a  jz      short loc_18002FC62
0x18002fc0c  cmp     byte ptr [rcx+19h], 2
0x18002fc10  jb      short loc_18002FC62
0x18002fc12  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002fc19  lea     edx, [rbx+17h]
0x18002fc1c  mov     rcx, [rcx+10h]
0x18002fc20  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18002fc27  call    WPP_SF_s
0x18002fc2c  jmp     short loc_18002FC62
0x18002fc2e  mov     eax, [rsp+2A8h+arg_30]
0x18002fc35  lea     rcx, [rbx+10h]; void *
0x18002fc39  mov     r8, r14; Size
0x18002fc3c  mov     [rbx+8], eax
0x18002fc3f  mov     rdx, r15; Src
0x18002fc42  mov     [rbx+0Ch], r14d
0x18002fc46  call    memcpy_0
0x18002fc4b  mov     rdx, rbx; Destination
0x18002fc4e  lea     rcx, [rsp+2A8h+var_288]; struct _CARD_CACHE_QUERY_INFO *
0x18002fc53  call    CspAddCardCacheItem
0x18002fc58  mov     edi, eax
0x18002fc5a  mov     rcx, rbx
0x18002fc5d  call    CspFreeH
0x18002fc62  mov     eax, edi
0x18002fc64  mov     rcx, [rsp+2A8h+var_48]
0x18002fc6c  xor     rcx, rsp; StackCookie
0x18002fc6f  call    __security_check_cookie
0x18002fc74  add     rsp, 278h
0x18002fc7b  pop     r15
0x18002fc7d  pop     r14
0x18002fc7f  pop     rdi
0x18002fc80  pop     rsi
0x18002fc81  pop     rbp
0x18002fc82  pop     rbx
0x18002fc83  retn
```
