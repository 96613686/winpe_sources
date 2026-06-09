# PAC_MarshallValidationInfo(_SAMPR_USER_ALL_INFORMATION *,_SAMPR_GET_GROUPS_BUFFER *,_SID_AND_ATTRIBUTES_LIST *,void *,_UNICODE_STRING *,_UNICODE_STRING *,uchar,uchar,_LARGE_INTEGER *,_LARGE_INTEGER *,_LSA_LAST_INTER_LOGON_INFO *,uchar * *,ulong *)

- ea: `0x1800370b8`
- end: `0x1800372b4`
- name: `?PAC_MarshallValidationInfo@@YAJPEAU_SAMPR_USER_ALL_INFORMATION@@PEAU_SAMPR_GET_GROUPS_BUFFER@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAXPEAU_UNICODE_STRING@@4EEPEAT_LARGE_INTEGER@@5PEAU_LSA_LAST_INTER_LOGON_INFO@@PEAPEAEPEAK@Z`
- size: `508`
- prototype: `__int64 __fastcall(struct _SAMPR_USER_ALL_INFORMATION *, struct _SAMPR_GET_GROUPS_BUFFER *, struct _SID_AND_ATTRIBUTES_LIST *, void *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned __int8, unsigned __int8, union _LARGE_INTEGER *, union _LARGE_INTEGER *, struct _LSA_LAST_INTER_LOGON_INFO *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180036fac`

## callees

- `0x180009770`
- `0x180012880`
- `0x180013304`
- `0x180023f80`
- `0x180036c10`
- `0x1800370b8`
- `0x1800377bc`

## pseudocode

```c
__int64 __fastcall PAC_MarshallValidationInfo(
        struct _SAMPR_USER_ALL_INFORMATION *a1,
        struct _SAMPR_GET_GROUPS_BUFFER *a2,
        const void **a3,
        void *a4,
        struct _UNICODE_STRING *a5,
        struct _UNICODE_STRING *a6,
        unsigned __int8 a7,
        unsigned __int8 a8,
        union _LARGE_INTEGER *a9,
        union _LARGE_INTEGER *a10,
        struct _LSA_LAST_INTER_LOGON_INFO *a11,
        unsigned __int8 **a12,
        unsigned int *a13)
{
  unsigned int v16; // r8d
  int v17; // edx
  int v18; // ecx
  void *v19; // rdi
  int v20; // r10d
  void *v21; // rax
  unsigned int v22; // ebx
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm1
  __int64 v31; // [rsp+20h] [rbp-E0h] BYREF
  int v32; // [rsp+28h] [rbp-D8h]
  int v33; // [rsp+2Ch] [rbp-D4h]
  int v34; // [rsp+30h] [rbp-D0h]
  int v35; // [rsp+34h] [rbp-CCh]
  __int64 v36; // [rsp+38h] [rbp-C8h]
  __int64 v37; // [rsp+40h] [rbp-C0h]
  __int64 v38; // [rsp+48h] [rbp-B8h]
  __int128 v39; // [rsp+50h] [rbp-B0h]
  __int128 v40; // [rsp+60h] [rbp-A0h]
  __int128 v41; // [rsp+70h] [rbp-90h]
  __int128 v42; // [rsp+80h] [rbp-80h]
  __int128 v43; // [rsp+90h] [rbp-70h]
  __int128 v44; // [rsp+A0h] [rbp-60h]
  __int16 v45; // [rsp+B0h] [rbp-50h]
  __int16 v46; // [rsp+B2h] [rbp-4Eh]
  int v47; // [rsp+B4h] [rbp-4Ch]
  int v48; // [rsp+B8h] [rbp-48h]
  int v49; // [rsp+BCh] [rbp-44h]
  __int64 v50; // [rsp+C0h] [rbp-40h]
  int v51; // [rsp+C8h] [rbp-38h]
  UNICODE_STRING v52; // [rsp+E0h] [rbp-20h]
  __int128 v53; // [rsp+F0h] [rbp-10h]
  void *v54; // [rsp+100h] [rbp+0h]
  int v55; // [rsp+110h] [rbp+10h]
  unsigned int v56; // [rsp+130h] [rbp+30h]
  void *v57; // [rsp+138h] [rbp+38h]

  memset_0((char *)&v31 + 4, 0, 0x134u);
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  if ( a3 )
    v16 = *(_DWORD *)a3;
  v20 = *((_DWORD *)a1 + 70);
  if ( (v20 & 0x1000) != 0 )
  {
    v17 = 0x40000;
    v18 = 0x40000;
  }
  v31 = *(_QWORD *)a1;
  v33 = 0x7FFFFFFF;
  v35 = 0x7FFFFFFF;
  v36 = *((_QWORD *)a1 + 2);
  v37 = *((_QWORD *)a1 + 4);
  v38 = *((_QWORD *)a1 + 5);
  v32 = -1;
  v34 = -1;
  if ( (v20 & 0x1000) != 0 )
  {
    v37 = 0x7FFFFFFFFFFFFFFFLL;
    v38 = 0x7FFFFFFFFFFFFFFFLL;
  }
  else
  {
    v18 = v17;
  }
  v45 = *((_WORD *)a1 + 153);
  v46 = *((_WORD *)a1 + 152);
  v47 = *((_DWORD *)a1 + 68);
  v48 = *((_DWORD *)a1 + 69);
  v49 = 0;
  v50 = 0;
  v55 = v20;
  v51 = v18 | 0x20;
  if ( v16 )
  {
    v56 = v16;
    v21 = MIDL_user_allocate(16LL * v16);
    v19 = v21;
    if ( !v21 )
      return (unsigned int)-1073741670;
    v57 = v21;
    if ( a3 )
      memcpy_0(v21, a3[1], 16LL * *(unsigned int *)a3);
  }
  v23 = *((_OWORD *)a1 + 3);
  v24 = *((_OWORD *)a1 + 4);
  v54 = a4;
  v39 = v23;
  v25 = *((_OWORD *)a1 + 7);
  v40 = v24;
  v26 = *((_OWORD *)a1 + 8);
  v41 = v25;
  v27 = *((_OWORD *)a1 + 5);
  v42 = v26;
  v28 = *((_OWORD *)a1 + 6);
  v43 = v27;
  v44 = v28;
  v29 = (__int128)*a5;
  v52 = g_ustrWorkstationName;
  v53 = v29;
  v22 = PAC_EncodeValidationInformation((struct _NETLOGON_VALIDATION_SAM_INFO3 *)&v31, a12, a13);
  if ( v19 )
    DigestFreeMemory(v19);
  return v22;
}

```

## disassembly

```asm
0x1800370b8  mov     [rsp-8+arg_8], rbx
0x1800370bd  push    rbp
0x1800370be  push    rsi
0x1800370bf  push    rdi
0x1800370c0  push    r12
0x1800370c2  push    r13
0x1800370c4  push    r14
0x1800370c6  push    r15
0x1800370c8  lea     rbp, [rsp-70h]
0x1800370cd  sub     rsp, 170h
0x1800370d4  mov     rax, cs:__security_cookie
0x1800370db  xor     rax, rsp
0x1800370de  mov     [rbp+0A0h+var_40], rax
0x1800370e2  mov     r15, [rbp+0A0h+arg_20]
0x1800370e9  mov     rsi, r8
0x1800370ec  mov     r12, [rbp+0A0h+arg_58]
0x1800370f3  mov     rbx, rcx
0x1800370f6  mov     r13, [rbp+0A0h+arg_60]
0x1800370fd  lea     rcx, [rsp+1A0h+var_17C]; void *
0x180037102  mov     r8d, 134h; Size
0x180037108  xor     edx, edx; Val
0x18003710a  mov     r14, r9
0x18003710d  call    memset_0
0x180037112  xor     r8d, r8d
0x180037115  xor     edx, edx
0x180037117  xor     ecx, ecx
0x180037119  xor     edi, edi
0x18003711b  test    rsi, rsi
0x18003711e  jz      short loc_180037123
0x180037120  mov     r8d, [rsi]
0x180037123  mov     r10d, [rbx+118h]
0x18003712a  mov     r9d, r10d
0x18003712d  and     r9d, 1000h
0x180037134  jz      short loc_18003713D
0x180037136  mov     edx, 40000h
0x18003713b  mov     ecx, edx
0x18003713d  mov     rax, [rbx]
0x180037140  or      r11d, 0FFFFFFFFh
0x180037144  mov     [rsp+20h], rax
0x180037149  mov     eax, 7FFFFFFFh
0x18003714e  mov     [rsp+1A0h+var_174], eax
0x180037152  mov     [rsp+1A0h+var_16C], eax
0x180037156  mov     rax, [rbx+10h]
0x18003715a  mov     [rsp+1A0h+var_168], rax
0x18003715f  mov     rax, [rbx+20h]
0x180037163  mov     [rsp+1A0h+var_160], rax
0x180037168  mov     rax, [rbx+28h]
0x18003716c  mov     [rsp+1A0h+var_158], rax
0x180037171  mov     [rsp+1A0h+var_178], r11d
0x180037176  mov     [rsp+1A0h+var_170], r11d
0x18003717b  test    r9d, r9d
0x18003717e  jz      short loc_180037199
0x180037180  mov     eax, 7FFFFFFFh
0x180037185  mov     dword ptr [rsp+1A0h+var_160], r11d
0x18003718a  mov     dword ptr [rsp+1A0h+var_160+4], eax
0x18003718e  mov     dword ptr [rsp+1A0h+var_158+4], eax
0x180037192  mov     dword ptr [rsp+1A0h+var_158], r11d
0x180037197  jmp     short loc_18003719B
0x180037199  mov     ecx, edx
0x18003719b  movzx   eax, word ptr [rbx+132h]
0x1800371a2  or      ecx, 20h
0x1800371a5  mov     [rbp+0A0h+var_F0], ax
0x1800371a9  movzx   eax, word ptr [rbx+130h]
0x1800371b0  mov     [rbp+0A0h+var_EE], ax
0x1800371b4  mov     eax, [rbx+110h]
0x1800371ba  mov     [rbp+0A0h+var_EC], eax
0x1800371bd  mov     eax, [rbx+114h]
0x1800371c3  mov     [rbp+0A0h+var_E8], eax
0x1800371c6  mov     [rbp+0A0h+var_E4], edi
0x1800371c9  mov     [rbp+0A0h+var_E0], rdi
0x1800371cd  mov     [rbp+0A0h+var_90], r10d
0x1800371d1  mov     [rbp+0A0h+var_D8], ecx
0x1800371d4  test    r8d, r8d
0x1800371d7  jz      short loc_180037217
0x1800371d9  mov     ecx, r8d
0x1800371dc  shl     rcx, 4; size
0x1800371e0  mov     [rbp+0A0h+var_70], r8d
0x1800371e4  call    MIDL_user_allocate
0x1800371e9  mov     rdi, rax
0x1800371ec  test    rax, rax
0x1800371ef  jnz     short loc_1800371FB
0x1800371f1  mov     ebx, 0C000009Ah
0x1800371f6  jmp     loc_18003728B
0x1800371fb  mov     [rbp+0A0h+var_68], rax
0x1800371ff  test    rsi, rsi
0x180037202  jz      short loc_180037217
0x180037204  mov     r8d, [rsi]
0x180037207  mov     rcx, rax; void *
0x18003720a  mov     rdx, [rsi+8]; Src
0x18003720e  shl     r8, 4; Size
0x180037212  call    memcpy_0
0x180037217  movups  xmm0, xmmword ptr [rbx+30h]
0x18003721b  mov     r8, r13; unsigned int *
0x18003721e  mov     rdx, r12; unsigned __int8 **
0x180037221  movups  xmm1, xmmword ptr [rbx+40h]
0x180037225  lea     rcx, [rsp+1A0h+var_180]; struct _NETLOGON_VALIDATION_SAM_INFO3 *
0x18003722a  mov     [rbp+0A0h+var_A0], r14
0x18003722e  movdqu  [rsp+1A0h+var_150], xmm0
0x180037234  movups  xmm0, xmmword ptr [rbx+70h]
0x180037238  movdqu  [rsp+1A0h+var_140], xmm1
0x18003723e  movups  xmm1, xmmword ptr [rbx+80h]
0x180037245  movdqu  [rsp+1A0h+var_130], xmm0
0x18003724b  movups  xmm0, xmmword ptr [rbx+50h]
0x18003724f  movdqu  [rbp+0A0h+var_120], xmm1
0x180037254  movups  xmm1, xmmword ptr [rbx+60h]
0x180037258  movdqu  [rbp+0A0h+var_110], xmm0
0x18003725d  movups  xmm0, xmmword ptr cs:g_ustrWorkstationName.Length
0x180037264  movdqu  [rbp+0A0h+var_100], xmm1
0x180037269  movups  xmm1, xmmword ptr [r15]
0x18003726d  movdqu  [rbp+0A0h+var_C0], xmm0
0x180037272  movdqu  [rbp+0A0h+var_B0], xmm1
0x180037277  call    ?PAC_EncodeValidationInformation@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAPEAEPEAK@Z; PAC_EncodeValidationInformation(_NETLOGON_VALIDATION_SAM_INFO3 *,uchar * *,ulong *)
0x18003727c  mov     ebx, eax
0x18003727e  test    rdi, rdi
0x180037281  jz      short loc_18003728B
0x180037283  mov     rcx, rdi; hMem
0x180037286  call    DigestFreeMemory
0x18003728b  mov     eax, ebx
0x18003728d  mov     rcx, [rbp+0A0h+var_40]
0x180037291  xor     rcx, rsp; StackCookie
0x180037294  call    __security_check_cookie
0x180037299  mov     rbx, [rsp+1A0h+arg_8]
0x1800372a1  add     rsp, 170h
0x1800372a8  pop     r15
0x1800372aa  pop     r14
0x1800372ac  pop     r13
0x1800372ae  pop     r12
0x1800372b0  pop     rdi
0x1800372b1  pop     rsi
0x1800372b2  pop     rbp
0x1800372b3  retn
```
