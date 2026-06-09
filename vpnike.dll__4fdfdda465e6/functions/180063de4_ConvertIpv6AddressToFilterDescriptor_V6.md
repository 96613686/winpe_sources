# ConvertIpv6AddressToFilterDescriptor_V6

- ea: `0x180063de4`
- end: `0x1800640c7`
- name: `ConvertIpv6AddressToFilterDescriptor_V6`
- size: `739`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180066084`

## callees

- `0x180063de4`
- `0x180075c80`
- `0x180075eec`
- `0x180075f5c`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063e3f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063e3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006407c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064085`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006407c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064085`
- `rtutils!TracePrintfExA` at `0x180063fc0`
- `rtutils!TracePrintfExA` at `0x180064069`
- `rtutils!TracePrintfExA` at `0x180063fc0`
- `rtutils!TracePrintfExA` at `0x180064069`

## string_xrefs

- `0x180063f65`: `MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d`
- `0x180064015`: `MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d`
- `0x180063fb4`: `MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d`
- `0x18006405d`: `MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d`

## pseudocode

```c
__int64 __fastcall ConvertIpv6AddressToFilterDescriptor_V6(HLOCAL *a1, unsigned int a2)
{
  unsigned int v2; // r15d
  BYTE *lpItemData; // rdi
  __int64 v6; // rcx
  unsigned int v7; // ebx
  unsigned __int8 *v8; // r12
  unsigned int v9; // r13d
  __int64 v10; // r15
  char *v11; // rdi
  __int64 v12; // r11
  int v13; // r8d
  int v14; // r9d
  int v15; // r9d
  __int128 v16; // xmm0
  __int64 v17; // rax
  DWORD v18; // eax
  DWORD v19; // ebx
  void *v20; // rsi
  DWORD v21; // eax
  LPVOID lpNewHeader; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lplpNewHeader; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v25[20]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h] BYREF
  char v28[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v2 = a2 - 1;
  lpNewHeader = 0;
  lplpNewHeader = 0;
  v26 = (BYTE *)LocalAlloc(0x40u, 52LL * (a2 - 1) + 64);
  lpItemData = v26;
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v7 = 0;
  memset(v25, 0, sizeof(v25));
  if ( a2 )
  {
    do
    {
      v8 = (unsigned __int8 *)*a1;
      v9 = 0;
      v10 = 16 * v7;
      v11 = (char *)*a1 + v10;
      do
      {
        v12 = 4 * v9++;
        v13 = (unsigned __int8)v11[v12];
        v14 = (v8[v12 + 2 + v10] << 8) + (v8[v12 + 1 + v10] << 16);
        v25[v12] = v13;
        v15 = v8[v12 + 3 + v10] + (v13 << 24) + v14;
        v25[(unsigned int)(v12 + 1)] = BYTE2(v15);
        v25[(unsigned int)(v12 + 2)] = BYTE1(v15);
        v25[(unsigned int)(v12 + 3)] = v15;
      }
      while ( v9 < 5 );
      lpItemData = v26;
      v16 = *(_OWORD *)&v25[1];
      v17 = v7++;
      v6 = 52 * v17;
      *(_DWORD *)&v26[v6 + 56] |= 0x11u;
      *(_DWORD *)&lpItemData[v6 + 48] = 128;
      *(_OWORD *)&lpItemData[v6 + 32] = v16;
    }
    while ( v7 < a2 );
    v2 = a2 - 1;
  }
  *((_DWORD *)lpItemData + 2) = 1;
  *(_DWORD *)lpItemData = 1;
  *((_DWORD *)lpItemData + 1) = a2;
  v18 = MprInfoCreate(v6, &lpNewHeader);
  v19 = v18;
  if ( v18 )
  {
    if ( gIsProtocolCommonTracingEnabled )
    {
      if ( *((_QWORD *)&xmmword_1800AB3E0 + 1) )
      {
        LOWORD(v27) = 0;
        FormatRRASErrorString(
          &v27,
          L"MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d",
          v18);
        ((void (__fastcall *)(__int64, _QWORD, int *))gProtocolCommonTemplateFunc)(
          gProtocolCommonEtwContext,
          *((_QWORD *)&xmmword_1800AB3E0 + 1),
          &v27);
      }
    }
    else if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d",
        v18);
    }
  }
  else
  {
    v20 = lpNewHeader;
    v21 = MprInfoBlockAdd(lpNewHeader, 0xFFFF0011, 52 * v2 + 64, 1u, lpItemData, &lplpNewHeader);
    v19 = v21;
    if ( v21 )
    {
      if ( gIsProtocolCommonTracingEnabled )
      {
        if ( *((_QWORD *)&xmmword_1800AB3E0 + 1) )
        {
          LOWORD(v27) = 0;
          FormatRRASErrorString(
            &v27,
            L"MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d",
            v21);
          ((void (__fastcall *)(__int64, _QWORD, int *))gProtocolCommonTemplateFunc)(
            gProtocolCommonEtwContext,
            *((_QWORD *)&xmmword_1800AB3E0 + 1),
            &v27);
        }
      }
      else if ( g_dwTraceId != -1 )
      {
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d",
          v21);
      }
      MprInfoDelete(v20);
    }
    else
    {
      LocalFree(*a1);
      LocalFree(lpItemData);
      MprInfoDelete(v20);
      *a1 = lplpNewHeader;
    }
  }
  return v19;
}

```

## disassembly

```asm
0x180063de4  mov     [rsp-8+arg_10], rbx
0x180063de9  push    rbp
0x180063dea  push    rsi
0x180063deb  push    rdi
0x180063dec  push    r12
0x180063dee  push    r13
0x180063df0  push    r14
0x180063df2  push    r15
0x180063df4  lea     rbp, [rsp-770h]
0x180063dfc  sub     rsp, 870h
0x180063e03  mov     rax, cs:__security_cookie
0x180063e0a  xor     rax, rsp
0x180063e0d  mov     [rbp+7A0h+var_40], rax
0x180063e14  lea     r15d, [rdx-1]
0x180063e18  mov     [rsp+8A0h+lpNewHeader], 0
0x180063e21  mov     esi, edx
0x180063e23  mov     eax, r15d
0x180063e26  imul    rdx, rax, 34h ; '4'
0x180063e2a  mov     r14, rcx
0x180063e2d  mov     [rsp+8A0h+var_868], 0
0x180063e36  add     rdx, 40h ; '@'; uBytes
0x180063e3a  mov     ecx, 40h ; '@'; uFlags
0x180063e3f  call    cs:__imp_LocalAlloc
0x180063e45  mov     [rsp+8A0h+var_848], rax
0x180063e4a  xor     edx, edx; Val
0x180063e4c  mov     rdi, rax
0x180063e4f  lea     rcx, [rsp+8A0h+var_83C]; void *
0x180063e54  xor     eax, eax
0x180063e56  mov     r8d, 7FCh; Size
0x180063e5c  mov     [rsp+8A0h+var_840], eax
0x180063e60  call    memset_0
0x180063e65  xor     eax, eax
0x180063e67  xor     ebx, ebx
0x180063e69  mov     [rsp+8A0h+var_850], eax
0x180063e6d  xorps   xmm0, xmm0
0x180063e70  movups  [rsp+8A0h+var_860], xmm0
0x180063e75  test    esi, esi
0x180063e77  jz      loc_180063F2C
0x180063e7d  mov     r12, [r14]
0x180063e80  mov     eax, ebx
0x180063e82  xor     r13d, r13d
0x180063e85  shl     eax, 4
0x180063e88  mov     r15d, eax
0x180063e8b  lea     rdi, [r12+rax]
0x180063e8f  lea     r11d, ds:0[r13*4]
0x180063e97  inc     r13d
0x180063e9a  movzx   r8d, byte ptr [r11+rdi]
0x180063e9f  lea     rdx, [r11+r12]
0x180063ea3  movzx   eax, byte ptr [rdx+r15+2]
0x180063ea9  movzx   r9d, byte ptr [rdx+r15+1]
0x180063eaf  shl     eax, 8
0x180063eb2  shl     r9d, 10h
0x180063eb6  add     r9d, eax
0x180063eb9  mov     byte ptr [rsp+r11+8A0h+var_860], r8b
0x180063ebe  mov     eax, r8d
0x180063ec1  shl     eax, 18h
0x180063ec4  add     r9d, eax
0x180063ec7  movzx   eax, byte ptr [rdx+r15+3]
0x180063ecd  add     r9d, eax
0x180063ed0  lea     eax, [r11+1]
0x180063ed4  mov     edx, r9d
0x180063ed7  shr     edx, 10h
0x180063eda  mov     byte ptr [rsp+rax+8A0h+var_860], dl
0x180063ede  lea     eax, [r11+2]
0x180063ee2  mov     edx, r9d
0x180063ee5  shr     edx, 8
0x180063ee8  mov     byte ptr [rsp+rax+8A0h+var_860], dl
0x180063eec  lea     eax, [r11+3]
0x180063ef0  mov     byte ptr [rsp+rax+8A0h+var_860], r9b
0x180063ef5  cmp     r13d, 5
0x180063ef9  jb      short loc_180063E8F
0x180063efb  mov     rdi, [rsp+8A0h+var_848]
0x180063f00  movups  xmm0, [rsp+8A0h+var_860+1]
0x180063f05  mov     eax, ebx
0x180063f07  inc     ebx
0x180063f09  imul    rcx, rax, 34h ; '4'; dwVersion
0x180063f0d  or      dword ptr [rcx+rdi+38h], 11h
0x180063f12  mov     dword ptr [rcx+rdi+30h], 80h
0x180063f1a  movdqu  xmmword ptr [rcx+rdi+20h], xmm0
0x180063f20  cmp     ebx, esi
0x180063f22  jb      loc_180063E7D
0x180063f28  lea     r15d, [rsi-1]
0x180063f2c  lea     rdx, [rsp+8A0h+lpNewHeader]; lplpNewHeader
0x180063f31  mov     dword ptr [rdi+8], 1
0x180063f38  mov     dword ptr [rdi], 1
0x180063f3e  mov     [rdi+4], esi
0x180063f41  call    MprInfoCreate
0x180063f46  mov     ebx, eax
0x180063f48  test    eax, eax
0x180063f4a  jz      short loc_180063FCB
0x180063f4c  cmp     cs:gIsProtocolCommonTracingEnabled, 0
0x180063f53  jz      short loc_180063FA2
0x180063f55  cmp     qword ptr cs:xmmword_1800AB3E0+8, 0
0x180063f5d  jz      loc_18006409B
0x180063f63  xor     ecx, ecx
0x180063f65  lea     rdx, aMprinfocreateF_2; "MprInfoCreate failed  in ConvertIpv6Add"...
0x180063f6c  mov     word ptr [rsp+8A0h+var_840], cx
0x180063f71  mov     r8d, eax
0x180063f74  lea     rcx, [rsp+8A0h+var_840]
0x180063f79  call    FormatRRASErrorString
0x180063f7e  mov     rdx, qword ptr cs:xmmword_1800AB3E0+8
0x180063f85  lea     r8, [rsp+8A0h+var_840]
0x180063f8a  mov     rcx, cs:gProtocolCommonEtwContext
0x180063f91  mov     rax, cs:gProtocolCommonTemplateFunc
0x180063f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f9d  jmp     loc_18006409B
0x180063fa2  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180063fa8  cmp     ecx, 0FFFFFFFFh
0x180063fab  jz      loc_18006409B
0x180063fb1  mov     r9d, eax
0x180063fb4  lea     r8, aMprinfocreateF_1; "MprInfoCreate failed  in ConvertIpv6Add"...
0x180063fbb  mov     edx, 0Ch; dwFlags
0x180063fc0  call    cs:__imp_TracePrintfExA
0x180063fc6  jmp     loc_18006409B
0x180063fcb  mov     rsi, [rsp+8A0h+lpNewHeader]
0x180063fd0  lea     rax, [rsp+8A0h+var_868]
0x180063fd5  imul    r8d, r15d, 34h ; '4'
0x180063fd9  mov     edx, 0FFFF0011h; dwInfoType
0x180063fde  mov     [rsp+8A0h+lplpNewHeader], rax; lplpNewHeader
0x180063fe3  mov     r9d, 1; dwItemCount
0x180063fe9  mov     rcx, rsi; lpHeader
0x180063fec  mov     [rsp+8A0h+lpItemData], rdi; lpItemData
0x180063ff1  add     r8d, 40h ; '@'; dwItemSize
0x180063ff5  call    MprInfoBlockAdd
0x180063ffa  mov     ebx, eax
0x180063ffc  test    eax, eax
0x180063ffe  jz      short loc_180064079
0x180064000  cmp     cs:gIsProtocolCommonTracingEnabled, 0
0x180064007  jz      short loc_18006404F
0x180064009  cmp     qword ptr cs:xmmword_1800AB3E0+8, 0
0x180064011  jz      short loc_18006406F
0x180064013  xor     eax, eax
0x180064015  lea     rdx, aMprinfocreateF_2; "MprInfoCreate failed  in ConvertIpv6Add"...
0x18006401c  mov     r8d, ebx
0x18006401f  mov     word ptr [rsp+8A0h+var_840], ax
0x180064024  lea     rcx, [rsp+8A0h+var_840]
0x180064029  call    FormatRRASErrorString
0x18006402e  mov     rdx, qword ptr cs:xmmword_1800AB3E0+8
0x180064035  lea     r8, [rsp+8A0h+var_840]
0x18006403a  mov     rcx, cs:gProtocolCommonEtwContext
0x180064041  mov     rax, cs:gProtocolCommonTemplateFunc
0x180064048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006404d  jmp     short loc_18006406F
0x18006404f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180064055  cmp     ecx, 0FFFFFFFFh
0x180064058  jz      short loc_18006406F
0x18006405a  mov     r9d, ebx
0x18006405d  lea     r8, aMprinfocreateF_1; "MprInfoCreate failed  in ConvertIpv6Add"...
0x180064064  mov     edx, 0Ch; dwFlags
0x180064069  call    cs:__imp_TracePrintfExA
0x18006406f  mov     rcx, rsi; lpHeader
0x180064072  call    MprInfoDelete
0x180064077  jmp     short loc_18006409B
0x180064079  mov     rcx, [r14]; hMem
0x18006407c  call    cs:__imp_LocalFree
0x180064082  mov     rcx, rdi; hMem
0x180064085  call    cs:__imp_LocalFree
0x18006408b  mov     rcx, rsi; lpHeader
0x18006408e  call    MprInfoDelete
0x180064093  mov     rax, [rsp+8A0h+var_868]
0x180064098  mov     [r14], rax
0x18006409b  mov     eax, ebx
0x18006409d  mov     rcx, [rbp+7A0h+var_40]
0x1800640a4  xor     rcx, rsp; StackCookie
0x1800640a7  call    __security_check_cookie
0x1800640ac  mov     rbx, [rsp+8A0h+arg_10]
0x1800640b4  add     rsp, 870h
0x1800640bb  pop     r15
0x1800640bd  pop     r14
0x1800640bf  pop     r13
0x1800640c1  pop     r12
0x1800640c3  pop     rdi
0x1800640c4  pop     rsi
0x1800640c5  pop     rbp
0x1800640c6  retn
```
