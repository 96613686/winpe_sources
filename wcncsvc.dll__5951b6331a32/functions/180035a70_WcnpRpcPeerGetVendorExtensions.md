# WcnpRpcPeerGetVendorExtensions

- ea: `0x180035a70`
- end: `0x180035c6a`
- name: `WcnpRpcPeerGetVendorExtensions`
- size: `506`
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
- `0x180035a70`
- `0x18003bddc`
- `0x180053004`
- `0x180056df2`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035b7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035b7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035c03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035c03`

## string_xrefs

- `0x180035b35`: `pVendorExtensions`

## pseudocode

```c
__int64 __fastcall WcnpRpcPeerGetVendorExtensions(__int64 a1, __int64 a2)
{
  _BYTE *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  __int64 v7; // rdx
  const char *v8; // r9
  int v10; // ebx
  __int64 v11; // rbx
  struct _RTL_CRITICAL_SECTION *v12; // rdi
  __int64 v13; // rdx
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // r8
  int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // r10
  __int64 v19; // [rsp+30h] [rbp-108h] BYREF
  _BYTE v20[208]; // [rsp+40h] [rbp-F8h] BYREF

  v19 = 0;
  memset_0(v20, 0, 0xC8u);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 146, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || v4[25] < 2u )
      return 2147500035LL;
    v7 = 147;
    v8 = "hPeer";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v4 + 2), v7, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, v8);
    return 2147500035LL;
  }
  if ( !a2 )
  {
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || v4[25] < 2u )
      return 2147500035LL;
    v7 = 148;
    v8 = "pVendorExtensions";
    goto LABEL_12;
  }
  if ( (unsigned __int8)CWcnRpcHandle::ValidateHandle(a1, 1, &v19) )
  {
    v11 = v19;
    v12 = (struct _RTL_CRITICAL_SECTION *)(v19 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
    v13 = *(_QWORD *)(v11 + 256);
    if ( v13 )
    {
      v14 = 25;
      v15 = (__int64)(*(_QWORD *)(v13 + 8) - *(_QWORD *)v13) >> 3;
      if ( v15 <= 0x19 )
      {
        v14 = (__int64)(*(_QWORD *)(v13 + 8) - *(_QWORD *)v13) >> 3;
        if ( !v15 )
          goto LABEL_22;
      }
      else
      {
        v15 = 25;
      }
      memcpy_0(v20, *(const void **)v13, 8 * v15);
    }
    else
    {
      v14 = 0;
    }
LABEL_22:
    v16 = WcnMarshalVendorExtensionBundle(v14, (__int64)v20, a2);
    v10 = v16;
    if ( v16 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        149,
        WPP_b6f763267c4d324c721a67068f3e4818_Traceguids,
        (unsigned int)v16);
    LeaveCriticalSection(v12);
    goto LABEL_27;
  }
  v10 = -2147024890;
LABEL_27:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v10 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v17 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v18 + 16), 150, (unsigned int)WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, v17, v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180035a70  mov     [rsp+arg_0], rbx
0x180035a75  mov     [rsp+arg_10], rbp
0x180035a7a  push    rsi
0x180035a7b  push    rdi
0x180035a7c  push    r14
0x180035a7e  sub     rsp, 120h
0x180035a85  mov     rax, cs:__security_cookie
0x180035a8c  xor     rax, rsp
0x180035a8f  mov     [rsp+138h+var_28], rax
0x180035a97  mov     rsi, rdx
0x180035a9a  mov     [rsp+138h+var_108], 0
0x180035aa3  mov     rbx, rcx
0x180035aa6  xor     edx, edx; Val
0x180035aa8  lea     rcx, [rsp+138h+var_F8]; void *
0x180035aad  mov     r8d, 0C8h; Size
0x180035ab3  call    memset_0
0x180035ab8  mov     r10, cs:WPP_GLOBAL_Control
0x180035abf  lea     rbp, WPP_GLOBAL_Control
0x180035ac6  lea     r14, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids
0x180035acd  mov     edi, 1
0x180035ad2  cmp     r10, rbp
0x180035ad5  jz      short loc_180035B00
0x180035ad7  cmp     byte ptr [r10+19h], 6
0x180035adc  jb      short loc_180035B00
0x180035ade  mov     ecx, edi; int
0x180035ae0  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180035ae5  mov     rcx, [r10+10h]
0x180035ae9  mov     edx, 92h
0x180035aee  mov     r9, rax
0x180035af1  mov     r8, r14
0x180035af4  call    WPP_SF_s
0x180035af9  mov     r10, cs:WPP_GLOBAL_Control
0x180035b00  test    rbx, rbx
0x180035b03  jnz     short loc_180035B1F
0x180035b05  cmp     r10, rbp
0x180035b08  jz      short loc_180035B48
0x180035b0a  cmp     byte ptr [r10+19h], 2
0x180035b0f  jb      short loc_180035B48
0x180035b11  mov     edx, 93h
0x180035b16  lea     r9, aHpeer; "hPeer"
0x180035b1d  jmp     short loc_180035B3C
0x180035b1f  test    rsi, rsi
0x180035b22  jnz     short loc_180035B52
0x180035b24  cmp     r10, rbp
0x180035b27  jz      short loc_180035B48
0x180035b29  cmp     byte ptr [r10+19h], 2
0x180035b2e  jb      short loc_180035B48
0x180035b30  mov     edx, 94h
0x180035b35  lea     r9, aPvendorextensi; "pVendorExtensions"
0x180035b3c  mov     rcx, [r10+10h]
0x180035b40  mov     r8, r14
0x180035b43  call    WPP_SF_s
0x180035b48  mov     eax, 80004003h
0x180035b4d  jmp     loc_180035C42
0x180035b52  lea     r8, [rsp+138h+var_108]
0x180035b57  mov     edx, edi
0x180035b59  mov     rcx, rbx
0x180035b5c  call    ?ValidateHandle@CWcnRpcHandle@@SA_NPEAXW4tagWCNPRPC_HANDLE_TYPE@@PEAPEAX@Z; CWcnRpcHandle::ValidateHandle(void *,tagWCNPRPC_HANDLE_TYPE,void * *)
0x180035b61  test    al, al
0x180035b63  jnz     short loc_180035B6F
0x180035b65  mov     ebx, 80070006h
0x180035b6a  jmp     loc_180035C09
0x180035b6f  mov     rbx, [rsp+138h+var_108]
0x180035b74  lea     rdi, [rbx+10h]
0x180035b78  mov     rcx, rdi; lpCriticalSection
0x180035b7b  call    cs:__imp_EnterCriticalSection
0x180035b81  mov     rdx, [rbx+100h]
0x180035b88  test    rdx, rdx
0x180035b8b  jz      short loc_180035BC2
0x180035b8d  mov     r8, [rdx+8]
0x180035b91  mov     ebx, 19h
0x180035b96  sub     r8, [rdx]
0x180035b99  sar     r8, 3
0x180035b9d  cmp     r8, rbx
0x180035ba0  jbe     short loc_180035BA7
0x180035ba2  mov     r8d, ebx
0x180035ba5  jmp     short loc_180035BAF
0x180035ba7  mov     rbx, r8
0x180035baa  test    r8, r8
0x180035bad  jz      short loc_180035BC4
0x180035baf  mov     rdx, [rdx]; Src
0x180035bb2  lea     rcx, [rsp+138h+var_F8]; void *
0x180035bb7  shl     r8, 3; Size
0x180035bbb  call    memcpy_0
0x180035bc0  jmp     short loc_180035BC4
0x180035bc2  xor     ebx, ebx
0x180035bc4  mov     r8, rsi
0x180035bc7  lea     rdx, [rsp+138h+var_F8]
0x180035bcc  mov     rcx, rbx
0x180035bcf  call    WcnMarshalVendorExtensionBundle
0x180035bd4  mov     ebx, eax
0x180035bd6  test    eax, eax
0x180035bd8  jns     short loc_180035C00
0x180035bda  mov     rcx, cs:WPP_GLOBAL_Control
0x180035be1  cmp     rcx, rbp
0x180035be4  jz      short loc_180035C00
0x180035be6  cmp     byte ptr [rcx+19h], 2
0x180035bea  jb      short loc_180035C00
0x180035bec  mov     rcx, [rcx+10h]
0x180035bf0  mov     edx, 95h
0x180035bf5  mov     r9d, eax
0x180035bf8  mov     r8, r14
0x180035bfb  call    WPP_SF_d
0x180035c00  mov     rcx, rdi; lpCriticalSection
0x180035c03  call    cs:__imp_LeaveCriticalSection
0x180035c09  mov     r10, cs:WPP_GLOBAL_Control
0x180035c10  cmp     r10, rbp
0x180035c13  jz      short loc_180035C40
0x180035c15  test    ebx, ebx
0x180035c17  js      short loc_180035C20
0x180035c19  cmp     byte ptr [r10+19h], 6
0x180035c1e  jb      short loc_180035C40
0x180035c20  or      ecx, 0FFFFFFFFh; int
0x180035c23  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180035c28  mov     rcx, [r10+10h]
0x180035c2c  mov     edx, 96h
0x180035c31  mov     r9, rax
0x180035c34  mov     [rsp+138h+var_118], ebx
0x180035c38  mov     r8, r14
0x180035c3b  call    WPP_SF_sd
0x180035c40  mov     eax, ebx
0x180035c42  mov     rcx, [rsp+138h+var_28]
0x180035c4a  xor     rcx, rsp; StackCookie
0x180035c4d  call    __security_check_cookie
0x180035c52  lea     r11, [rsp+138h+var_18]
0x180035c5a  mov     rbx, [r11+20h]
0x180035c5e  mov     rbp, [r11+30h]
0x180035c62  mov     rsp, r11
0x180035c65  pop     r14
0x180035c67  pop     rdi
0x180035c68  pop     rsi
0x180035c69  retn
```
