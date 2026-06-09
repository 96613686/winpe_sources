# ConfigCiPackageFamilyNameCheckEventLog(_UNICODE_STRING const *,unsigned __int64,void const *,uchar,uchar,long)

- ea: `0x180040970`
- end: `0x180040cd7`
- name: `?ConfigCiPackageFamilyNameCheckEventLog@@YAJPEBU_UNICODE_STRING@@_KPEBXEEJ@Z`
- size: `871`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, __int64, _DWORD *, __int64, unsigned __int8, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043670`

## callees

- `0x18002640c`
- `0x180027a70`
- `0x180040970`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040a48`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040b09`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040a48`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040b09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040c8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040c9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040c8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040c9d`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180040c7f`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180040c7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConfigCiPackageFamilyNameCheckEventLog(
        const struct _UNICODE_STRING *a1,
        __int64 a2,
        _DWORD *a3,
        __int64 a4,
        unsigned __int8 a5,
        char a6)
{
  __int16 v8; // bx
  HLOCAL v9; // rax
  void *v10; // r14
  __int64 *v11; // rsi
  __int16 v12; // r15
  HLOCAL v13; // rax
  void *v14; // rbx
  __int64 *v15; // r9
  int v16; // r8d
  int Length; // ecx
  int v18; // edx
  bool v19; // cf
  ULONG v20; // edi
  SIZE_T uBytes; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v24; // [rsp+4Ch] [rbp-B4h] BYREF
  __int16 v25; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+58h] [rbp-A8h] BYREF
  REGHANDLE RegHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v28; // [rsp+68h] [rbp-98h] BYREF
  __int128 v29; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-70h] BYREF
  PWSTR Buffer; // [rsp+A0h] [rbp-60h]
  int v32; // [rsp+A8h] [rbp-58h]
  int v33; // [rsp+ACh] [rbp-54h]
  __int64 *v34; // [rsp+B0h] [rbp-50h]
  __int64 v35; // [rsp+B8h] [rbp-48h]
  __int16 *v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  __int64 v38; // [rsp+D0h] [rbp-30h]
  int v39; // [rsp+D8h] [rbp-28h]
  int v40; // [rsp+DCh] [rbp-24h]
  __int16 *v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  __int64 v43; // [rsp+F0h] [rbp-10h]
  int v44; // [rsp+F8h] [rbp-8h]
  int v45; // [rsp+FCh] [rbp-4h]
  __int64 *v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]
  char *v48; // [rsp+110h] [rbp+10h]
  __int64 v49; // [rsp+118h] [rbp+18h]
  char *v50; // [rsp+120h] [rbp+20h]
  __int64 v51; // [rsp+128h] [rbp+28h]
  __int64 v52; // [rsp+188h] [rbp+88h] BYREF

  v52 = a2;
  v26 = 0;
  RegHandle = 0;
  uBytes = 0x400000000LL;
  v28 = 0;
  v29 = 0;
  if ( !a1 || !a3 || (int)GetEventHandle(&RegHandle) < 0 )
  {
    v20 = -1073741811;
    return v20 | 0x10000000;
  }
  if ( (unsigned int)SIPolicyQueryOneSecurityPolicy(
                       a3,
                       &qword_1800691C8,
                       &qword_1800691B8,
                       asc_1800691A8,
                       (char *)&uBytes + 4,
                       0,
                       &uBytes) != -1073741789
    || (v8 = uBytes, (unsigned int)(uBytes - 1) > 0xFFFD) )
  {
    v10 = 0;
LABEL_11:
    v11 = &qword_1800691F8;
    goto LABEL_12;
  }
  v9 = LocalAlloc(0x40u, (unsigned int)uBytes);
  v10 = v9;
  if ( !v9 )
    goto LABEL_11;
  *((_QWORD *)&v28 + 1) = v9;
  WORD1(v28) = v8;
  if ( (int)SIPolicyQueryOneSecurityPolicy(
              a3,
              &qword_1800691C8,
              &qword_1800691B8,
              asc_1800691A8,
              (char *)&uBytes + 4,
              &v28,
              &uBytes) < 0
    || HIDWORD(uBytes) != 3 )
  {
    goto LABEL_11;
  }
  v11 = (__int64 *)&v28;
LABEL_12:
  LODWORD(uBytes) = 0;
  if ( (unsigned int)SIPolicyQueryOneSecurityPolicy(
                       a3,
                       &qword_1800691C8,
                       &qword_1800691B8,
                       &qword_1800691D8,
                       (char *)&uBytes + 4,
                       0,
                       &uBytes) != -1073741789
    || (v12 = uBytes, (unsigned int)(uBytes - 1) > 0xFFFD) )
  {
    v14 = 0;
LABEL_19:
    v15 = &qword_1800691E8;
    goto LABEL_20;
  }
  v13 = LocalAlloc(0x40u, (unsigned int)uBytes);
  v14 = v13;
  if ( !v13 )
    goto LABEL_19;
  *((_QWORD *)&v29 + 1) = v13;
  WORD1(v29) = v12;
  if ( (int)SIPolicyQueryOneSecurityPolicy(
              a3,
              &qword_1800691C8,
              &qword_1800691B8,
              &qword_1800691D8,
              (char *)&uBytes + 4,
              &v29,
              &uBytes) < 0
    || HIDWORD(uBytes) != 3 )
  {
    goto LABEL_19;
  }
  v15 = (__int64 *)&v29;
LABEL_20:
  v16 = *(unsigned __int16 *)v15;
  Length = a1->Length;
  v18 = *(unsigned __int16 *)v11;
  v23 = a1->Length >> 1;
  v24 = (unsigned __int16)v18 >> 1;
  v19 = a3[10] < 6u;
  v25 = (unsigned __int16)v16 >> 1;
  v26 = *((_QWORD *)a3 + 4);
  UserData.Ptr = (ULONGLONG)&v23;
  Buffer = a1->Buffer;
  v34 = &v52;
  v36 = &v24;
  v38 = v11[1];
  v41 = &v25;
  v43 = v15[1];
  v46 = &v26;
  v32 = Length;
  v39 = v18;
  v48 = (char *)a3 + (-(__int64)v19 & 0xFFFFFFFFFFFFFD50uLL) + 704;
  v44 = v16;
  v50 = &a6;
  *(_QWORD *)&UserData.Size = 2;
  v33 = 0;
  v35 = 8;
  v37 = 2;
  v40 = 0;
  v42 = 2;
  v45 = 0;
  v47 = 8;
  v49 = 16;
  v51 = 4;
  v20 = EventWrite(RegHandle, &ConfigCiPackageFamilyNameCheckErr, 0xAu, &UserData);
  if ( v10 )
    LocalFree(v10);
  if ( v14 )
    LocalFree(v14);
  return v20 | 0x10000000;
}

```

## disassembly

```asm
0x180040970  mov     [rsp-8+arg_0], rbx
0x180040975  mov     [rsp-8+arg_8], rdx
0x18004097a  push    rbp
0x18004097b  push    rsi
0x18004097c  push    rdi
0x18004097d  push    r12
0x18004097f  push    r13
0x180040981  push    r14
0x180040983  push    r15
0x180040985  lea     rbp, [rsp-40h]
0x18004098a  sub     rsp, 140h
0x180040991  mov     rax, cs:__security_cookie
0x180040998  xor     rax, rsp
0x18004099b  mov     [rbp+70h+var_40], rax
0x18004099f  xor     r12d, r12d
0x1800409a2  mov     dword ptr [rsp+170h+uBytes+4], 4
0x1800409aa  mov     [rsp+170h+var_118], r12
0x1800409af  xorps   xmm0, xmm0
0x1800409b2  mov     [rsp+170h+RegHandle], r12
0x1800409b7  xorps   xmm1, xmm1
0x1800409ba  mov     dword ptr [rsp+170h+uBytes], r12d
0x1800409bf  mov     rdi, r8
0x1800409c2  mov     r13, rcx
0x1800409c5  movups  [rsp+170h+var_108], xmm0
0x1800409ca  movups  [rsp+170h+var_F8], xmm1
0x1800409cf  test    rcx, rcx
0x1800409d2  jz      loc_180040CA5
0x1800409d8  test    r8, r8
0x1800409db  jz      loc_180040CA5
0x1800409e1  lea     rcx, [rsp+170h+RegHandle]; unsigned __int64 *
0x1800409e6  call    ?GetEventHandle@@YAJPEA_K@Z; GetEventHandle(unsigned __int64 *)
0x1800409eb  test    eax, eax
0x1800409ed  js      loc_180040CA5
0x1800409f3  lea     rax, [rsp+170h+uBytes]
0x1800409f8  mov     rcx, rdi
0x1800409fb  mov     [rsp+170h+var_140], rax
0x180040a00  lea     r15, qword_1800691B8
0x180040a07  lea     rax, [rsp+170h+uBytes+4]
0x180040a0c  mov     [rsp+170h+var_148], r12
0x180040a11  lea     r9, asc_1800691A8; "\b\n"
0x180040a18  mov     [rsp+170h+var_150], rax
0x180040a1d  mov     r8, r15
0x180040a20  lea     rdx, qword_1800691C8
0x180040a27  call    SIPolicyQueryOneSecurityPolicy
0x180040a2c  cmp     eax, 0C0000023h
0x180040a31  jnz     short loc_180040AA9
0x180040a33  mov     ebx, dword ptr [rsp+170h+uBytes]
0x180040a37  lea     eax, [rbx-1]
0x180040a3a  cmp     eax, 0FFFDh
0x180040a3f  ja      short loc_180040AA9
0x180040a41  mov     edx, ebx; uBytes
0x180040a43  lea     ecx, [r12+40h]; uFlags
0x180040a48  call    cs:__imp_LocalAlloc
0x180040a4e  mov     r14, rax
0x180040a51  test    rax, rax
0x180040a54  jz      short loc_180040AAC
0x180040a56  mov     qword ptr [rsp+170h+var_108+8], rax
0x180040a5b  lea     r9, asc_1800691A8; "\b\n"
0x180040a62  lea     rax, [rsp+170h+uBytes]
0x180040a67  mov     word ptr [rsp+170h+var_108+2], bx
0x180040a6c  mov     [rsp+170h+var_140], rax
0x180040a71  lea     rdx, qword_1800691C8
0x180040a78  lea     rax, [rsp+170h+var_108]
0x180040a7d  mov     r8, r15
0x180040a80  mov     [rsp+170h+var_148], rax
0x180040a85  mov     rcx, rdi
0x180040a88  lea     rax, [rsp+170h+uBytes+4]
0x180040a8d  mov     [rsp+170h+var_150], rax
0x180040a92  call    SIPolicyQueryOneSecurityPolicy
0x180040a97  test    eax, eax
0x180040a99  js      short loc_180040AAC
0x180040a9b  cmp     dword ptr [rsp+170h+uBytes+4], 3
0x180040aa0  jnz     short loc_180040AAC
0x180040aa2  lea     rsi, [rsp+170h+var_108]
0x180040aa7  jmp     short loc_180040AB3
0x180040aa9  mov     r14, r12
0x180040aac  lea     rsi, qword_1800691F8
0x180040ab3  lea     rax, [rsp+170h+uBytes]
0x180040ab8  mov     dword ptr [rsp+170h+uBytes], r12d
0x180040abd  mov     [rsp+170h+var_140], rax
0x180040ac2  lea     r9, qword_1800691D8
0x180040ac9  lea     rax, [rsp+170h+uBytes+4]
0x180040ace  mov     [rsp+170h+var_148], r12
0x180040ad3  mov     r8, r15
0x180040ad6  mov     [rsp+170h+var_150], rax
0x180040adb  lea     rdx, qword_1800691C8
0x180040ae2  mov     rcx, rdi
0x180040ae5  call    SIPolicyQueryOneSecurityPolicy
0x180040aea  cmp     eax, 0C0000023h
0x180040aef  jnz     short loc_180040B6E
0x180040af1  mov     r15d, dword ptr [rsp+170h+uBytes]
0x180040af6  lea     eax, [r15-1]
0x180040afa  cmp     eax, 0FFFDh
0x180040aff  ja      short loc_180040B6E
0x180040b01  mov     edx, r15d; uBytes
0x180040b04  mov     ecx, 40h ; '@'; uFlags
0x180040b09  call    cs:__imp_LocalAlloc
0x180040b0f  mov     rbx, rax
0x180040b12  test    rax, rax
0x180040b15  jz      short loc_180040B71
0x180040b17  mov     qword ptr [rbp+70h+var_F8+8], rax
0x180040b1b  lea     r9, qword_1800691D8
0x180040b22  lea     rax, [rsp+170h+uBytes]
0x180040b27  mov     word ptr [rsp+170h+var_F8+2], r15w
0x180040b2d  mov     [rsp+170h+var_140], rax
0x180040b32  lea     r8, qword_1800691B8
0x180040b39  lea     rax, [rsp+170h+var_F8]
0x180040b3e  mov     rcx, rdi
0x180040b41  mov     [rsp+170h+var_148], rax
0x180040b46  lea     rdx, qword_1800691C8
0x180040b4d  lea     rax, [rsp+170h+uBytes+4]
0x180040b52  mov     [rsp+170h+var_150], rax
0x180040b57  call    SIPolicyQueryOneSecurityPolicy
0x180040b5c  test    eax, eax
0x180040b5e  js      short loc_180040B71
0x180040b60  cmp     dword ptr [rsp+170h+uBytes+4], 3
0x180040b65  jnz     short loc_180040B71
0x180040b67  lea     r9, [rsp+170h+var_F8]
0x180040b6c  jmp     short loc_180040B78
0x180040b6e  mov     rbx, r12
0x180040b71  lea     r9, qword_1800691E8
0x180040b78  movzx   r8d, word ptr [r9]
0x180040b7c  movzx   ecx, word ptr [r13+0]
0x180040b81  movzx   edx, word ptr [rsi]
0x180040b84  movzx   eax, cx
0x180040b87  shr     ax, 1
0x180040b8a  mov     [rsp+170h+var_128], ax
0x180040b8f  movzx   eax, dx
0x180040b92  shr     ax, 1
0x180040b95  mov     [rsp+170h+var_124], ax
0x180040b9a  movzx   eax, r8w
0x180040b9e  shr     ax, 1
0x180040ba1  cmp     dword ptr [rdi+28h], 6
0x180040ba5  mov     [rsp+170h+var_120], ax
0x180040baa  mov     rax, [rdi+20h]
0x180040bae  mov     [rsp+170h+var_118], rax
0x180040bb3  lea     rax, [rsp+170h+var_128]
0x180040bb8  mov     [rbp+70h+UserData.Ptr], rax
0x180040bbc  mov     rax, [r13+8]
0x180040bc0  mov     [rbp+70h+var_D0], rax
0x180040bc4  lea     rax, [rbp+70h+arg_8]
0x180040bcb  mov     [rbp+70h+var_C0], rax
0x180040bcf  lea     rax, [rsp+170h+var_124]
0x180040bd4  mov     [rbp+70h+var_B0], rax
0x180040bd8  mov     rax, [rsi+8]
0x180040bdc  mov     [rbp+70h+var_A0], rax
0x180040be0  lea     rax, [rsp+170h+var_120]
0x180040be5  mov     [rbp+70h+var_90], rax
0x180040be9  mov     rax, [r9+8]
0x180040bed  lea     r9, [rbp+70h+UserData]; UserData
0x180040bf1  mov     [rbp+70h+var_80], rax
0x180040bf5  lea     rax, [rsp+170h+var_118]
0x180040bfa  mov     [rbp+70h+var_70], rax
0x180040bfe  sbb     rax, rax
0x180040c01  and     rax, 0FFFFFFFFFFFFFD50h
0x180040c07  mov     [rbp+70h+var_C8], ecx
0x180040c0a  mov     rcx, [rsp+170h+RegHandle]; RegHandle
0x180040c0f  add     rax, 2C0h
0x180040c15  add     rax, rdi
0x180040c18  mov     [rbp+70h+var_98], edx
0x180040c1b  mov     [rbp+70h+var_60], rax
0x180040c1f  lea     rdx, ConfigCiPackageFamilyNameCheckErr; EventDescriptor
0x180040c26  lea     rax, [rbp+70h+arg_28]
0x180040c2d  mov     [rbp+70h+var_78], r8d
0x180040c31  mov     r8d, 0Ah; UserDataCount
0x180040c37  mov     [rbp+70h+var_50], rax
0x180040c3b  mov     qword ptr [rbp+70h+UserData.Size], 2
0x180040c43  mov     [rbp+70h+var_C4], r12d
0x180040c47  mov     [rbp+70h+var_B8], 8
0x180040c4f  mov     [rbp+70h+var_A8], 2
0x180040c57  mov     [rbp+70h+var_94], r12d
0x180040c5b  mov     [rbp+70h+var_88], 2
0x180040c63  mov     [rbp+70h+var_74], r12d
0x180040c67  mov     [rbp+70h+var_68], 8
0x180040c6f  mov     [rbp+70h+var_58], 10h
0x180040c77  mov     [rbp+70h+var_48], 4
0x180040c7f  call    cs:__imp_EventWrite
0x180040c85  mov     edi, eax
0x180040c87  test    r14, r14
0x180040c8a  jz      short loc_180040C95
0x180040c8c  mov     rcx, r14; hMem
0x180040c8f  call    cs:__imp_LocalFree
0x180040c95  test    rbx, rbx
0x180040c98  jz      short loc_180040CAA
0x180040c9a  mov     rcx, rbx; hMem
0x180040c9d  call    cs:__imp_LocalFree
0x180040ca3  jmp     short loc_180040CAA
0x180040ca5  mov     edi, 0C000000Dh
0x180040caa  bts     edi, 1Ch
0x180040cae  mov     eax, edi
0x180040cb0  mov     rcx, [rbp+70h+var_40]
0x180040cb4  xor     rcx, rsp; StackCookie
0x180040cb7  call    __security_check_cookie
0x180040cbc  mov     rbx, [rsp+170h+arg_0]
0x180040cc4  add     rsp, 140h
0x180040ccb  pop     r15
0x180040ccd  pop     r14
0x180040ccf  pop     r13
0x180040cd1  pop     r12
0x180040cd3  pop     rdi
0x180040cd4  pop     rsi
0x180040cd5  pop     rbp
0x180040cd6  retn
```
