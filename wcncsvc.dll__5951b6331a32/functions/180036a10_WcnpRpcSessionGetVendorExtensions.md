# WcnpRpcSessionGetVendorExtensions

- ea: `0x180036a10`
- end: `0x180036c2e`
- name: `WcnpRpcSessionGetVendorExtensions`
- size: `542`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180001e16`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x180033904`
- `0x180036a10`
- `0x18003bddc`
- `0x180053004`
- `0x180056df2`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036b26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036b26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036bc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036bc3`

## pseudocode

```c
__int64 __fastcall WcnpRpcSessionGetVendorExtensions(__int64 a1, int a2, __int64 a3)
{
  __int64 v4; // rsi
  _BYTE *v6; // r10
  const char *Indent; // rax
  __int64 v8; // r10
  __int64 v9; // rdx
  const char *v10; // r9
  int v12; // ebx
  __int64 v13; // rdi
  struct _RTL_CRITICAL_SECTION *v14; // rbp
  unsigned __int64 v15; // rbx
  __int64 v16; // rdx
  unsigned __int64 v17; // r8
  int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // r10
  __int64 v21; // [rsp+30h] [rbp-118h] BYREF
  _BYTE v22[208]; // [rsp+40h] [rbp-108h] BYREF

  v4 = a2;
  v21 = 0;
  memset_0(v22, 0, 0xC8u);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 157, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, Indent);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || v6[25] < 2u )
      return 2147500035LL;
    v9 = 158;
    v10 = "hSession";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v6 + 2), v9, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, v10);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || v6[25] < 2u )
      return 2147500035LL;
    v9 = 159;
    v10 = "pBundle";
    goto LABEL_12;
  }
  if ( !(unsigned __int8)CWcnRpcHandle::ValidateHandle(a1, 2, &v21) )
  {
    v12 = -2147024890;
    goto LABEL_29;
  }
  v13 = v21;
  v14 = (struct _RTL_CRITICAL_SECTION *)(v21 + 1536);
  EnterCriticalSection((LPCRITICAL_SECTION)(v21 + 1536));
  if ( (int)v4 < 3 )
  {
    v15 = 0;
    if ( (int)v4 >= 0 )
    {
      _mm_lfence();
      v16 = *(_QWORD *)(v13 + 8 * v4 + 1512);
      if ( v16 )
      {
        v15 = 25;
        v17 = (__int64)(*(_QWORD *)(v16 + 8) - *(_QWORD *)v16) >> 3;
        if ( v17 > 0x19 )
        {
          v17 = 25;
LABEL_23:
          memcpy_0(v22, *(const void **)v16, 8 * v17);
          goto LABEL_24;
        }
        v15 = (__int64)(*(_QWORD *)(v16 + 8) - *(_QWORD *)v16) >> 3;
        if ( v17 )
          goto LABEL_23;
      }
    }
LABEL_24:
    v18 = WcnMarshalVendorExtensionBundle(v15, (__int64)v22, a3);
    v12 = v18;
    if ( v18 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        160,
        WPP_b6f763267c4d324c721a67068f3e4818_Traceguids,
        (unsigned int)v18);
    goto LABEL_28;
  }
  v12 = -2147024809;
LABEL_28:
  LeaveCriticalSection(v14);
LABEL_29:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v12 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v19 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v20 + 16), 161, (unsigned int)WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, v19, v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180036a10  mov     [rsp+arg_0], rbx
0x180036a15  mov     [rsp+arg_8], rbp
0x180036a1a  push    rsi
0x180036a1b  push    rdi
0x180036a1c  push    r12
0x180036a1e  push    r14
0x180036a20  push    r15
0x180036a22  sub     rsp, 120h
0x180036a29  mov     rax, cs:__security_cookie
0x180036a30  xor     rax, rsp
0x180036a33  mov     [rsp+148h+var_38], rax
0x180036a3b  mov     r14, r8
0x180036a3e  movsxd  rsi, edx
0x180036a41  mov     rbx, rcx
0x180036a44  mov     [rsp+148h+var_118], 0
0x180036a4d  xor     edx, edx; Val
0x180036a4f  lea     rcx, [rsp+148h+var_108]; void *
0x180036a54  mov     r8d, 0C8h; Size
0x180036a5a  call    memset_0
0x180036a5f  mov     r10, cs:WPP_GLOBAL_Control
0x180036a66  lea     r15, WPP_GLOBAL_Control
0x180036a6d  lea     r12, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids
0x180036a74  cmp     r10, r15
0x180036a77  jz      short loc_180036AA5
0x180036a79  cmp     byte ptr [r10+19h], 6
0x180036a7e  jb      short loc_180036AA5
0x180036a80  mov     ecx, 1; int
0x180036a85  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180036a8a  mov     rcx, [r10+10h]
0x180036a8e  mov     edx, 9Dh
0x180036a93  mov     r9, rax
0x180036a96  mov     r8, r12
0x180036a99  call    WPP_SF_s
0x180036a9e  mov     r10, cs:WPP_GLOBAL_Control
0x180036aa5  test    rbx, rbx
0x180036aa8  jnz     short loc_180036AC4
0x180036aaa  cmp     r10, r15
0x180036aad  jz      short loc_180036AED
0x180036aaf  cmp     byte ptr [r10+19h], 2
0x180036ab4  jb      short loc_180036AED
0x180036ab6  mov     edx, 9Eh
0x180036abb  lea     r9, aHsession; "hSession"
0x180036ac2  jmp     short loc_180036AE1
0x180036ac4  test    r14, r14
0x180036ac7  jnz     short loc_180036AF7
0x180036ac9  cmp     r10, r15
0x180036acc  jz      short loc_180036AED
0x180036ace  cmp     byte ptr [r10+19h], 2
0x180036ad3  jb      short loc_180036AED
0x180036ad5  mov     edx, 9Fh
0x180036ada  lea     r9, aPbundle; "pBundle"
0x180036ae1  mov     rcx, [r10+10h]
0x180036ae5  mov     r8, r12
0x180036ae8  call    WPP_SF_s
0x180036aed  mov     eax, 80004003h
0x180036af2  jmp     loc_180036C02
0x180036af7  lea     r8, [rsp+148h+var_118]
0x180036afc  mov     edx, 2
0x180036b01  mov     rcx, rbx
0x180036b04  call    ?ValidateHandle@CWcnRpcHandle@@SA_NPEAXW4tagWCNPRPC_HANDLE_TYPE@@PEAPEAX@Z; CWcnRpcHandle::ValidateHandle(void *,tagWCNPRPC_HANDLE_TYPE,void * *)
0x180036b09  test    al, al
0x180036b0b  jnz     short loc_180036B17
0x180036b0d  mov     ebx, 80070006h
0x180036b12  jmp     loc_180036BC9
0x180036b17  mov     rdi, [rsp+148h+var_118]
0x180036b1c  lea     rbp, [rdi+600h]
0x180036b23  mov     rcx, rbp; lpCriticalSection
0x180036b26  call    cs:__imp_EnterCriticalSection
0x180036b2c  cmp     esi, 3
0x180036b2f  jl      short loc_180036B3B
0x180036b31  mov     ebx, 80070057h
0x180036b36  jmp     loc_180036BC0
0x180036b3b  xor     ebx, ebx
0x180036b3d  test    esi, esi
0x180036b3f  js      short loc_180036B84
0x180036b41  lfence
0x180036b44  mov     rdx, [rdi+rsi*8+5E8h]
0x180036b4c  test    rdx, rdx
0x180036b4f  jz      short loc_180036B84
0x180036b51  mov     r8, [rdx+8]
0x180036b55  mov     ebx, 19h
0x180036b5a  sub     r8, [rdx]
0x180036b5d  sar     r8, 3
0x180036b61  cmp     r8, rbx
0x180036b64  jbe     short loc_180036B6B
0x180036b66  mov     r8d, ebx
0x180036b69  jmp     short loc_180036B73
0x180036b6b  mov     rbx, r8
0x180036b6e  test    r8, r8
0x180036b71  jz      short loc_180036B84
0x180036b73  mov     rdx, [rdx]; Src
0x180036b76  lea     rcx, [rsp+148h+var_108]; void *
0x180036b7b  shl     r8, 3; Size
0x180036b7f  call    memcpy_0
0x180036b84  mov     r8, r14
0x180036b87  lea     rdx, [rsp+148h+var_108]
0x180036b8c  mov     rcx, rbx
0x180036b8f  call    WcnMarshalVendorExtensionBundle
0x180036b94  mov     ebx, eax
0x180036b96  test    eax, eax
0x180036b98  jns     short loc_180036BC0
0x180036b9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ba1  cmp     rcx, r15
0x180036ba4  jz      short loc_180036BC0
0x180036ba6  cmp     byte ptr [rcx+19h], 2
0x180036baa  jb      short loc_180036BC0
0x180036bac  mov     rcx, [rcx+10h]
0x180036bb0  mov     edx, 0A0h
0x180036bb5  mov     r9d, eax
0x180036bb8  mov     r8, r12
0x180036bbb  call    WPP_SF_d
0x180036bc0  mov     rcx, rbp; lpCriticalSection
0x180036bc3  call    cs:__imp_LeaveCriticalSection
0x180036bc9  mov     r10, cs:WPP_GLOBAL_Control
0x180036bd0  cmp     r10, r15
0x180036bd3  jz      short loc_180036C00
0x180036bd5  test    ebx, ebx
0x180036bd7  js      short loc_180036BE0
0x180036bd9  cmp     byte ptr [r10+19h], 6
0x180036bde  jb      short loc_180036C00
0x180036be0  or      ecx, 0FFFFFFFFh; int
0x180036be3  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180036be8  mov     rcx, [r10+10h]
0x180036bec  mov     edx, 0A1h
0x180036bf1  mov     r9, rax
0x180036bf4  mov     [rsp+148h+var_128], ebx
0x180036bf8  mov     r8, r12
0x180036bfb  call    WPP_SF_sd
0x180036c00  mov     eax, ebx
0x180036c02  mov     rcx, [rsp+148h+var_38]
0x180036c0a  xor     rcx, rsp; StackCookie
0x180036c0d  call    __security_check_cookie
0x180036c12  lea     r11, [rsp+148h+var_28]
0x180036c1a  mov     rbx, [r11+30h]
0x180036c1e  mov     rbp, [r11+38h]
0x180036c22  mov     rsp, r11
0x180036c25  pop     r15
0x180036c27  pop     r14
0x180036c29  pop     r12
0x180036c2b  pop     rdi
0x180036c2c  pop     rsi
0x180036c2d  retn
```
