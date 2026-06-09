# CDlpActionLayoutUsb::FindOemFilePath(ushort const *,ushort const *,int *)

- ea: `0x180017148`
- end: `0x180017317`
- name: `?FindOemFilePath@CDlpActionLayoutUsb@@AEAAJPEBG0PEAH@Z`
- size: `463`
- prototype: `__int64 __fastcall(CDlpActionLayoutUsb *this, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180021988`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x180017148`
- `0x18001fd60`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001723f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017272`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800172b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800172e7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001723f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017272`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800172b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800172e7`

## string_xrefs

- `0x18001718a`: `CDlpActionLayoutUsb::FindOemFilePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDlpActionLayoutUsb::FindOemFilePath(
        CDlpActionLayoutUsb *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int *a4)
{
  __int64 v8; // rcx
  unsigned int v9; // edi
  int v10; // eax
  __int64 v11; // rcx
  unsigned int i; // esi
  unsigned int j; // esi
  int v14; // eax
  int lpString2; // [rsp+20h] [rbp-58h]

  if ( !a2 )
  {
    v8 = *((_QWORD *)this + 11);
    v9 = -2147024809;
    if ( !v8 )
      goto LABEL_25;
    lpString2 = 1326;
    goto LABEL_4;
  }
  if ( !a3 )
  {
    v8 = *((_QWORD *)this + 11);
    v9 = -2147024809;
    if ( !v8 )
      goto LABEL_25;
    lpString2 = 1327;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v8 = *((_QWORD *)this + 11);
    v9 = -2147024809;
    if ( !v8 )
      goto LABEL_25;
    lpString2 = 1328;
LABEL_4:
    v10 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v8,
            4u,
            (__int64)L"%s(%d): Result = 0x%X",
            L"CDlpActionLayoutUsb::FindOemFilePath",
            lpString2,
            -2147024809);
    v11 = (unsigned int)v10;
    if ( v10 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
    goto LABEL_25;
  }
  v9 = 0;
  for ( i = 0; i < *((_DWORD *)this + 251); ++i )
  {
    if ( CompareStringW(0x409u, 1u, a2, -1, *(PCNZWCH *)(*((_QWORD *)this + 126) + 8LL * (int)i), -1) == 2
      || CompareStringW(0x409u, 1u, a3, -1, *(PCNZWCH *)(*((_QWORD *)this + 128) + 8LL * (int)i), -1) == 2 )
    {
LABEL_23:
      v14 = 1;
      goto LABEL_24;
    }
  }
  for ( j = 0; ; ++j )
  {
    v14 = 0;
    if ( j >= *((_DWORD *)this + 259) )
      break;
    if ( CompareStringW(0x409u, 1u, a2, -1, *(PCNZWCH *)(*((_QWORD *)this + 130) + 8LL * (int)j), -1) == 2
      || CompareStringW(0x409u, 1u, a3, -1, *(PCNZWCH *)(*((_QWORD *)this + 132) + 8LL * (int)j), -1) == 2 )
    {
      goto LABEL_23;
    }
  }
LABEL_24:
  *a4 = v14;
LABEL_25:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  return v9;
}

```

## disassembly

```asm
0x180017148  push    rbx
0x18001714a  push    rbp
0x18001714b  push    rsi
0x18001714c  push    rdi
0x18001714d  push    r12
0x18001714f  push    r13
0x180017151  push    r14
0x180017153  push    r15
0x180017155  sub     rsp, 38h
0x180017159  mov     r14, r9
0x18001715c  mov     rbp, r8
0x18001715f  mov     r15, rdx
0x180017162  mov     rbx, rcx
0x180017165  test    rdx, rdx
0x180017168  jnz     short loc_1800171B7
0x18001716a  mov     rcx, [rcx+58h]
0x18001716e  mov     eax, 80070057h
0x180017173  mov     edi, eax
0x180017175  test    rcx, rcx
0x180017178  jz      loc_1800172FD
0x18001717e  mov     [rsp+78h+cchCount2], eax
0x180017182  mov     dword ptr [rsp+78h+lpString2], 52Eh
0x18001718a  lea     r9, aCdlpactionlayo_3; "CDlpActionLayoutUsb::FindOemFilePath"
0x180017191  mov     edx, 4
0x180017196  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18001719d  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800171a2  mov     ecx, eax
0x1800171a4  test    eax, eax
0x1800171a6  jns     short loc_1800171AD
0x1800171a8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800171ad  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800171b2  jmp     loc_1800172FD
0x1800171b7  test    rbp, rbp
0x1800171ba  jnz     short loc_1800171DE
0x1800171bc  mov     rcx, [rcx+58h]
0x1800171c0  mov     eax, 80070057h
0x1800171c5  mov     edi, eax
0x1800171c7  test    rcx, rcx
0x1800171ca  jz      loc_1800172FD
0x1800171d0  mov     [rsp+78h+cchCount2], eax
0x1800171d4  mov     dword ptr [rsp+78h+lpString2], 52Fh
0x1800171dc  jmp     short loc_18001718A
0x1800171de  test    r14, r14
0x1800171e1  jnz     short loc_180017205
0x1800171e3  mov     rcx, [rcx+58h]
0x1800171e7  mov     eax, 80070057h
0x1800171ec  mov     edi, eax
0x1800171ee  test    rcx, rcx
0x1800171f1  jz      loc_1800172FD
0x1800171f7  mov     [rsp+78h+cchCount2], eax
0x1800171fb  mov     dword ptr [rsp+78h+lpString2], 530h
0x180017203  jmp     short loc_18001718A
0x180017205  xor     edi, edi
0x180017207  xor     esi, esi
0x180017209  lea     r13d, [rdi+1]
0x18001720d  cmp     esi, [rbx+3ECh]
0x180017213  jnb     short loc_180017282
0x180017215  mov     rax, [rbx+3F0h]
0x18001721c  or      r9d, 0FFFFFFFFh; cchCount1
0x180017220  movsxd  r12, esi
0x180017223  mov     r8, r15; lpString1
0x180017226  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001722e  mov     edx, r13d; dwCmpFlags
0x180017231  mov     ecx, 409h; Locale
0x180017236  mov     rax, [rax+r12*8]
0x18001723a  mov     [rsp+78h+lpString2], rax; lpString2
0x18001723f  call    cs:__imp_CompareStringW
0x180017245  cmp     eax, 2
0x180017248  jz      loc_1800172F7
0x18001724e  mov     rax, [rbx+400h]
0x180017255  or      r9d, 0FFFFFFFFh; cchCount1
0x180017259  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x18001725e  mov     r8, rbp; lpString1
0x180017261  mov     edx, r13d; dwCmpFlags
0x180017264  mov     rcx, [rax+r12*8]
0x180017268  mov     [rsp+78h+lpString2], rcx; lpString2
0x18001726d  mov     ecx, 409h; Locale
0x180017272  call    cs:__imp_CompareStringW
0x180017278  cmp     eax, 2
0x18001727b  jz      short loc_1800172F7
0x18001727d  add     esi, r13d
0x180017280  jmp     short loc_18001720D
0x180017282  xor     esi, esi
0x180017284  xor     eax, eax
0x180017286  cmp     esi, [rbx+40Ch]
0x18001728c  jnb     short loc_1800172FA
0x18001728e  mov     rax, [rbx+410h]
0x180017295  or      r9d, 0FFFFFFFFh; cchCount1
0x180017299  movsxd  r12, esi
0x18001729c  mov     r8, r15; lpString1
0x18001729f  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800172a7  mov     edx, r13d; dwCmpFlags
0x1800172aa  mov     ecx, 409h; Locale
0x1800172af  mov     rax, [rax+r12*8]
0x1800172b3  mov     [rsp+78h+lpString2], rax; lpString2
0x1800172b8  call    cs:__imp_CompareStringW
0x1800172be  cmp     eax, 2
0x1800172c1  jz      short loc_1800172F7
0x1800172c3  mov     rax, [rbx+420h]
0x1800172ca  or      r9d, 0FFFFFFFFh; cchCount1
0x1800172ce  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x1800172d3  mov     r8, rbp; lpString1
0x1800172d6  mov     edx, r13d; dwCmpFlags
0x1800172d9  mov     rcx, [rax+r12*8]
0x1800172dd  mov     [rsp+78h+lpString2], rcx; lpString2
0x1800172e2  mov     ecx, 409h; Locale
0x1800172e7  call    cs:__imp_CompareStringW
0x1800172ed  cmp     eax, 2
0x1800172f0  jz      short loc_1800172F7
0x1800172f2  add     esi, r13d
0x1800172f5  jmp     short loc_180017284
0x1800172f7  mov     eax, r13d
0x1800172fa  mov     [r14], eax
0x1800172fd  mov     ecx, edi
0x1800172ff  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180017304  mov     eax, edi
0x180017306  add     rsp, 38h
0x18001730a  pop     r15
0x18001730c  pop     r14
0x18001730e  pop     r13
0x180017310  pop     r12
0x180017312  pop     rdi
0x180017313  pop     rsi
0x180017314  pop     rbp
0x180017315  pop     rbx
0x180017316  retn
```
