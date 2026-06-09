# WsAddUse

- ea: `0x18000b900`
- end: `0x18000be7e`
- name: `WsAddUse`
- size: `1406`
- prototype: `__int64 __usercall@<rax>(PLUID SourceLuid@<rcx>, PLUID@<rdx>, int, __int64, int, __int64, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001750`
- `0x18002be90`

## callees

- `0x18000b4f0`
- `0x18000b900`
- `0x1800119b0`
- `0x180031ae4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000bb7e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000bbb5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000be38`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000bb7e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000bbb5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000be38`
- `ntdll!RtlCopyLuid` at `0x18000bc22`
- `ntdll!RtlCopyLuid` at `0x18000bc3f`
- `ntdll!RtlCopyLuid` at `0x18000bc22`
- `ntdll!RtlCopyLuid` at `0x18000bc3f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000b92b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000b92b`
- `ntdll!NtClose` at `0x18000bb46`
- `ntdll!NtClose` at `0x18000bb46`
- `ntdll!RtlReleaseResource` at `0x18000baac`
- `ntdll!RtlReleaseResource` at `0x18000bb32`
- `ntdll!RtlReleaseResource` at `0x18000bbee`
- `ntdll!RtlReleaseResource` at `0x18000be6d`
- `ntdll!RtlReleaseResource` at `0x18000baac`
- `ntdll!RtlReleaseResource` at `0x18000bb32`
- `ntdll!RtlReleaseResource` at `0x18000bbee`
- `ntdll!RtlReleaseResource` at `0x18000be6d`
- `ntdll!RtlCompareUnicodeString` at `0x18000ba61`
- `ntdll!RtlCompareUnicodeString` at `0x18000ba61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be17`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bd1e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bdf4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bd1e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bdf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be0b`

## pseudocode

```c
__int64 __fastcall WsAddUse(
        PLUID SourceLuid,
        PLUID a2,
        void *a3,
        __int64 a4,
        unsigned int a5,
        WCHAR *a6,
        unsigned int a7,
        __int64 a8,
        int a9,
        _OWORD *a10,
        _QWORD *a11,
        _QWORD *a12)
{
  __int64 LowPart; // rdx
  __int64 v16; // r9
  __int64 v17; // rbx
  unsigned int v18; // edi
  _QWORD *v19; // rsi
  unsigned __int64 v20; // r15
  __int64 v21; // r12
  _QWORD *v22; // rbx
  BOOL v23; // ebp
  _QWORD *v24; // r14
  WCHAR *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rax
  DWORD NewEntry; // ebx
  _DWORD *v30; // rax
  unsigned __int64 v31; // rcx
  unsigned int v32; // edi
  _DWORD *v33; // rax
  char *v34; // r14
  int v35; // ecx
  char *v36; // rax
  int v37; // eax
  SIZE_T v38; // rdx
  _DWORD *v39; // rax
  _DWORD *v40; // rbx
  char *v41; // [rsp+60h] [rbp-58h] BYREF
  UNICODE_STRING String2; // [rsp+68h] [rbp-50h] BYREF
  UNICODE_STRING String1; // [rsp+78h] [rbp-40h] BYREF

  v41 = 0;
  if ( !RtlAcquireResourceExclusive(&Resource, 1u) )
    return 2140;
  v16 = Use;
  v17 = 0;
  v18 = -1;
  while ( (unsigned int)v17 < dword_180052110 )
  {
    LowPart = SourceLuid->LowPart;
    if ( *SourceLuid == *(_QWORD *)(Use + 24 * v17 + 8) || *SourceLuid == *(_QWORD *)(Use + 24 * v17 + 16) )
      goto LABEL_8;
    if ( v18 == -1 && !*(_QWORD *)(Use + 24 * v17) )
      v18 = v17;
    v17 = (unsigned int)(v17 + 1);
  }
  if ( v18 != -1 )
  {
LABEL_38:
    v17 = 24LL * v18;
    RtlCopyLuid((PLUID)(v17 + v16 + 8), SourceLuid);
    RtlCopyLuid((PLUID)(v17 + Use + 16), a2);
    v16 = Use;
    LODWORD(v17) = v18;
LABEL_8:
    v19 = 0;
    v20 = -1;
    v21 = 24LL * (unsigned int)v17;
    v22 = *(_QWORD **)(v21 + v16);
    if ( !v22 )
      goto LABEL_19;
    v23 = 0;
    v24 = 0;
    do
    {
      if ( !v23 )
      {
        v25 = (WCHAR *)(v22[1] + 8LL);
        String1 = 0;
        v26 = -1;
        String2 = 0;
        do
          ++v26;
        while ( v25[v26] );
        String1.Buffer = v25;
        String1.MaximumLength = 2 * (v26 + 1);
        String1.Length = String1.MaximumLength;
        v27 = -1;
        do
          ++v27;
        while ( a6[v27] );
        String2.Buffer = a6;
        String2.MaximumLength = 2 * (v27 + 1);
        String2.Length = String2.MaximumLength;
        if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
        {
          v24 = v22;
          v23 = v22[2] == 0;
        }
      }
      v19 = v22;
      v22 = (_QWORD *)*v22;
    }
    while ( v22 );
    if ( v24 )
    {
      if ( !a4 && !v24[2] )
      {
        v30 = (_DWORD *)v24[1];
        ++*((_DWORD *)v24 + 7);
        ++*v30;
        RtlReleaseResource(&Resource);
        NtClose(a3);
        return 0;
      }
      NewEntry = WsCreateNewEntry(
                   (unsigned int)&v41,
                   (_DWORD)a3,
                   a4,
                   a5,
                   0,
                   0,
                   a8,
                   a9,
                   (__int64)a10,
                   (__int64)a11,
                   (__int64)a12);
      if ( NewEntry )
        goto LABEL_21;
      v33 = (_DWORD *)v24[1];
      v34 = v41;
      *((_QWORD *)v41 + 1) = v33;
      ++*v33;
    }
    else
    {
LABEL_19:
      if ( a5 > 0xFFFF )
      {
LABEL_20:
        NewEntry = 2317;
LABEL_21:
        RtlReleaseResource(&Resource);
        return NewEntry;
      }
      LODWORD(v41) = 2 * a5 + 98;
      NetpULongRoundUp((unsigned int)v41, 2, &v41);
      if ( a4 )
        v35 = *(unsigned __int16 *)(a8 + 2);
      else
        v35 = 0;
      v36 = (char *)LocalAlloc(0x40u, (unsigned int)(v35 + (_DWORD)v41));
      v34 = v36;
      if ( !v36 )
        goto LABEL_58;
      *(_QWORD *)v36 = 0;
      *((_DWORD *)v36 + 6) = a5;
      *((_DWORD *)v36 + 7) = 1;
      *((_QWORD *)v36 + 4) = a3;
      v37 = dword_1800512F0;
      *((_DWORD *)v34 + 10) = dword_1800512F0;
      *((_DWORD *)v34 + 14) = a9;
      if ( a10 )
        *(_OWORD *)(v34 + 60) = *a10;
      if ( a11 )
        *(_QWORD *)(v34 + 76) = *a11;
      if ( a12 )
        *(_QWORD *)(v34 + 84) = *a12;
      dword_1800512F0 = (v37 + 1) & 0x7FFFFFFF;
      if ( a4 )
      {
        *((_QWORD *)v34 + 2) = v34 + 96;
        _o_wcscpy_s(v34 + 96, a5 + 1, a4);
        v31 = (unsigned __int64)&v34[2 * a5 + 98];
        if ( v31 + 2 >= v31 )
          v20 = (v31 + 1) & 0xFFFFFFFFFFFFFFFEuLL;
        *((_QWORD *)v34 + 6) = v20;
        _o_wcscpy_s(v20, (unsigned __int64)*(unsigned __int16 *)(a8 + 2) >> 1, *(_QWORD *)(a8 + 8));
      }
      else
      {
        *((_QWORD *)v34 + 2) = 0;
        *((_QWORD *)v34 + 6) = 0;
      }
      if ( a6 )
      {
        v38 = 2 * a7 + 18;
        if ( (unsigned int)v38 < 0x10 || (unsigned int)v38 >> 1 < a7 )
          goto LABEL_20;
        v39 = LocalAlloc(0x40u, v38);
        v40 = v39;
        if ( !v39 )
        {
          LocalFree(v34);
LABEL_58:
          NewEntry = GetLastError();
          if ( NewEntry )
            goto LABEL_21;
          goto LABEL_61;
        }
        _o_wcscpy_s(v39 + 2, a7 + 1, a6);
        v40[1] = a7;
        *v40 = 1;
        *((_QWORD *)v34 + 1) = v40;
      }
    }
LABEL_61:
    if ( v19 )
      *v19 = v34;
    else
      *(_QWORD *)(v21 + Use) = v34;
    RtlReleaseResource(&Resource);
    return 0;
  }
  v32 = WsGrowTable(&Use, LowPart, (unsigned int)dword_180052110, Use);
  if ( !v32 )
  {
    v16 = Use;
    v18 = v17;
    goto LABEL_38;
  }
  RtlReleaseResource(&Resource);
  return v32;
}

```

## disassembly

```asm
0x18000b900  mov     [rsp+Handle], r8
0x18000b905  push    rbp
0x18000b906  push    rsi
0x18000b907  push    r13
0x18000b909  sub     rsp, 0A0h
0x18000b910  mov     rbp, rdx
0x18000b913  mov     [rsp+0B8h+var_58], 0
0x18000b91c  mov     rsi, rcx
0x18000b91f  mov     dl, 1; Wait
0x18000b921  lea     rcx, Resource; Resource
0x18000b928  mov     r13, r9
0x18000b92b  call    cs:__imp_RtlAcquireResourceExclusive
0x18000b932  nop     dword ptr [rax+rax+00h]
0x18000b937  test    al, al
0x18000b939  jz      loc_18000BBC6
0x18000b93f  mov     r8d, cs:dword_180052110
0x18000b946  mov     r9, cs:Use
0x18000b94d  mov     [rsp+0B8h+arg_0], rbx
0x18000b955  xor     ebx, ebx
0x18000b957  mov     [rsp+0B8h+arg_8], rdi
0x18000b95f  mov     edi, 0FFFFFFFFh
0x18000b964  cmp     ebx, r8d
0x18000b967  jnb     loc_18000BBD0
0x18000b96d  mov     edx, [rsi]
0x18000b96f  lea     rcx, [rbx+rbx*2]
0x18000b973  cmp     edx, [r9+rcx*8+8]
0x18000b978  jz      short loc_18000B992
0x18000b97a  cmp     edx, [r9+rcx*8+10h]
0x18000b97f  jz      loc_18000BB59
0x18000b985  cmp     edi, 0FFFFFFFFh
0x18000b988  jz      loc_18000BAEF
0x18000b98e  inc     ebx
0x18000b990  jmp     short loc_18000B964
0x18000b992  mov     eax, [r9+rcx*8+0Ch]
0x18000b997  cmp     [rsi+4], eax
0x18000b99a  jnz     short loc_18000B97A
0x18000b99c  mov     rdi, [rsp+0B8h+arg_28]
0x18000b9a4  xor     esi, esi
0x18000b9a6  mov     [rsp+0B8h+arg_18], r12
0x18000b9ae  mov     eax, ebx
0x18000b9b0  mov     [rsp+0B8h+var_20], r14
0x18000b9b8  mov     [rsp+0B8h+var_28], r15
0x18000b9c0  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18000b9c7  lea     rcx, [rax+rax*2]
0x18000b9cb  lea     r12, ds:0[rcx*8]
0x18000b9d3  mov     rbx, [r12+r9]
0x18000b9d7  test    rbx, rbx
0x18000b9da  jz      loc_18000BA8D
0x18000b9e0  xor     ebp, ebp
0x18000b9e2  xor     r14d, r14d
0x18000b9e5  test    ebp, ebp
0x18000b9e7  jnz     loc_18000BA75
0x18000b9ed  mov     rcx, [rbx+8]
0x18000b9f1  xorps   xmm0, xmm0
0x18000b9f4  xorps   xmm1, xmm1
0x18000b9f7  add     rcx, 8
0x18000b9fb  movups  xmmword ptr [rsp+0B8h+String1.Length], xmm0
0x18000ba00  mov     rax, r15
0x18000ba03  movups  xmmword ptr [rsp+0B8h+String2.Length], xmm1
0x18000ba08  nop     dword ptr [rax+rax+00000000h]
0x18000ba10  inc     rax
0x18000ba13  cmp     word ptr [rcx+rax*2], 0
0x18000ba18  jnz     short loc_18000BA10
0x18000ba1a  inc     ax
0x18000ba1d  mov     [rsp+0B8h+String1.Buffer], rcx
0x18000ba25  add     ax, ax
0x18000ba28  mov     [rsp+0B8h+String1.MaximumLength], ax
0x18000ba2d  mov     [rsp+0B8h+String1.Length], ax
0x18000ba32  mov     rax, r15
0x18000ba35  inc     rax
0x18000ba38  cmp     word ptr [rdi+rax*2], 0
0x18000ba3d  jnz     short loc_18000BA35
0x18000ba3f  inc     ax
0x18000ba42  mov     [rsp+0B8h+String2.Buffer], rdi
0x18000ba47  add     ax, ax
0x18000ba4a  lea     rdx, [rsp+0B8h+String2]; String2
0x18000ba4f  mov     r8b, 1; CaseInsensitive
0x18000ba52  mov     [rsp+0B8h+String2.MaximumLength], ax
0x18000ba57  lea     rcx, [rsp+0B8h+String1]; String1
0x18000ba5c  mov     [rsp+0B8h+String2.Length], ax
0x18000ba61  call    cs:__imp_RtlCompareUnicodeString
0x18000ba68  nop     dword ptr [rax+rax+00h]
0x18000ba6d  test    eax, eax
0x18000ba6f  jz      loc_18000BAFC
0x18000ba75  mov     rsi, rbx
0x18000ba78  mov     rbx, [rbx]
0x18000ba7b  test    rbx, rbx
0x18000ba7e  jnz     loc_18000B9E5
0x18000ba84  test    r14, r14
0x18000ba87  jnz     loc_18000BB0E
0x18000ba8d  mov     ebx, [rsp+0B8h+arg_20]
0x18000ba94  cmp     ebx, 0FFFFh
0x18000ba9a  jbe     loc_18000BCE4
0x18000baa0  mov     ebx, 90Dh
0x18000baa5  lea     rcx, Resource; Resource
0x18000baac  call    cs:__imp_RtlReleaseResource
0x18000bab3  nop     dword ptr [rax+rax+00h]
0x18000bab8  mov     eax, ebx
0x18000baba  mov     r14, [rsp+0B8h+var_20]
0x18000bac2  mov     r12, [rsp+0B8h+arg_18]
0x18000baca  mov     r15, [rsp+0B8h+var_28]
0x18000bad2  mov     rbx, [rsp+0B8h+arg_0]
0x18000bada  mov     rdi, [rsp+0B8h+arg_8]
0x18000bae2  add     rsp, 0A0h
0x18000bae9  pop     r13
0x18000baeb  pop     rsi
0x18000baec  pop     rbp
0x18000baed  retn
0x18000baef  cmp     qword ptr [r9+rcx*8], 0
0x18000baf4  cmovz   edi, ebx
0x18000baf7  jmp     loc_18000B98E
0x18000bafc  xor     ebp, ebp
0x18000bafe  mov     r14, rbx
0x18000bb01  cmp     [rbx+10h], rbp
0x18000bb05  setz    bpl
0x18000bb09  jmp     loc_18000BA75
0x18000bb0e  test    r13, r13
0x18000bb11  jnz     loc_18000BC59
0x18000bb17  cmp     [r14+10h], r13
0x18000bb1b  jnz     loc_18000BC59
0x18000bb21  mov     rax, [r14+8]
0x18000bb25  lea     rcx, Resource; Resource
0x18000bb2c  inc     dword ptr [r14+1Ch]
0x18000bb30  inc     dword ptr [rax]
0x18000bb32  call    cs:__imp_RtlReleaseResource
0x18000bb39  nop     dword ptr [rax+rax+00h]
0x18000bb3e  mov     rcx, [rsp+0B8h+Handle]; Handle
0x18000bb46  call    cs:__imp_NtClose
0x18000bb4d  nop     dword ptr [rax+rax+00h]
0x18000bb52  xor     eax, eax
0x18000bb54  jmp     loc_18000BABA
0x18000bb59  mov     eax, [r9+rcx*8+14h]
0x18000bb5e  cmp     [rsi+4], eax
0x18000bb61  jnz     loc_18000B985
0x18000bb67  jmp     loc_18000B99C
0x18000bb6c  lea     eax, [rbx+1]
0x18000bb6f  mov     r8, r13
0x18000bb72  lea     rcx, [r14+60h]
0x18000bb76  mov     edx, eax
0x18000bb78  mov     [r14+10h], rcx
0x18000bb7c  mov     ebx, eax
0x18000bb7e  call    cs:__imp__o_wcscpy_s
0x18000bb85  nop     dword ptr [rax+rax+00h]
0x18000bb8a  lea     rcx, [rbx+30h]
0x18000bb8e  lea     rcx, [r14+rcx*2]
0x18000bb92  lea     rax, [rcx+2]
0x18000bb96  cmp     rax, rcx
0x18000bb99  jbe     short loc_18000BBA3
0x18000bb9b  lea     r15, [rcx+1]
0x18000bb9f  and     r15, 0FFFFFFFFFFFFFFFEh
0x18000bba3  mov     [r14+30h], r15
0x18000bba7  mov     rcx, r15
0x18000bbaa  movzx   edx, word ptr [rbp+2]
0x18000bbae  mov     r8, [rbp+8]
0x18000bbb2  shr     rdx, 1
0x18000bbb5  call    cs:__imp__o_wcscpy_s
0x18000bbbc  nop     dword ptr [rax+rax+00h]
0x18000bbc1  jmp     loc_18000BDC3
0x18000bbc6  mov     eax, 85Ch
0x18000bbcb  jmp     loc_18000BAE2
0x18000bbd0  cmp     edi, 0FFFFFFFFh
0x18000bbd3  jnz     short loc_18000BC0A
0x18000bbd5  lea     rcx, Use
0x18000bbdc  call    WsGrowTable
0x18000bbe1  mov     edi, eax
0x18000bbe3  test    eax, eax
0x18000bbe5  jz      short loc_18000BC01
0x18000bbe7  lea     rcx, Resource; Resource
0x18000bbee  call    cs:__imp_RtlReleaseResource
0x18000bbf5  nop     dword ptr [rax+rax+00h]
0x18000bbfa  mov     eax, edi
0x18000bbfc  jmp     loc_18000BAD2
0x18000bc01  mov     r9, cs:Use
0x18000bc08  mov     edi, ebx
0x18000bc0a  mov     eax, edi
0x18000bc0c  mov     rdx, rsi; SourceLuid
0x18000bc0f  lea     rcx, [rax+rax*2]
0x18000bc13  lea     rbx, ds:0[rcx*8]
0x18000bc1b  lea     rcx, [r9+8]
0x18000bc1f  add     rcx, rbx; DestinationLuid
0x18000bc22  call    cs:__imp_RtlCopyLuid
0x18000bc29  nop     dword ptr [rax+rax+00h]
0x18000bc2e  mov     rcx, cs:Use
0x18000bc35  mov     rdx, rbp; SourceLuid
0x18000bc38  add     rcx, 10h
0x18000bc3c  add     rcx, rbx; DestinationLuid
0x18000bc3f  call    cs:__imp_RtlCopyLuid
0x18000bc46  nop     dword ptr [rax+rax+00h]
0x18000bc4b  mov     r9, cs:Use
0x18000bc52  mov     ebx, edi
0x18000bc54  jmp     loc_18000B99C
0x18000bc59  mov     rax, [rsp+0B8h+arg_58]
0x18000bc61  lea     rcx, [rsp+0B8h+var_58]
0x18000bc66  mov     r9d, [rsp+0B8h+arg_20]
0x18000bc6e  mov     r8, r13
0x18000bc71  mov     rdx, [rsp+0B8h+Handle]
0x18000bc79  mov     [rsp+0B8h+var_68], rax
0x18000bc7e  mov     rax, [rsp+0B8h+arg_50]
0x18000bc86  mov     [rsp+0B8h+var_70], rax
0x18000bc8b  mov     rax, [rsp+0B8h+arg_48]
0x18000bc93  mov     [rsp+0B8h+var_78], rax
0x18000bc98  mov     eax, [rsp+0B8h+arg_40]
0x18000bc9f  mov     [rsp+0B8h+var_80], eax
0x18000bca3  mov     rax, [rsp+0B8h+arg_38]
0x18000bcab  mov     [rsp+0B8h+var_88], rax
0x18000bcb0  mov     [rsp+0B8h+var_90], 0
0x18000bcb8  mov     [rsp+0B8h+var_98], 0
0x18000bcc1  call    WsCreateNewEntry
0x18000bcc6  mov     ebx, eax
0x18000bcc8  test    eax, eax
0x18000bcca  jnz     loc_18000BAA5
0x18000bcd0  mov     rax, [r14+8]
0x18000bcd4  mov     r14, [rsp+0B8h+var_58]
0x18000bcd9  mov     [r14+8], rax
0x18000bcdd  inc     dword ptr [rax]
0x18000bcdf  jmp     loc_18000BE51
0x18000bce4  lea     ecx, ds:62h[rbx*2]
0x18000bceb  mov     edx, 2
0x18000bcf0  lea     r8, [rsp+0B8h+var_58]
0x18000bcf5  mov     dword ptr [rsp+0B8h+var_58], ecx
0x18000bcf9  call    NetpULongRoundUp
0x18000bcfe  mov     rbp, [rsp+0B8h+arg_38]
0x18000bd06  test    r13, r13
0x18000bd09  jz      short loc_18000BD11
0x18000bd0b  movzx   ecx, word ptr [rbp+2]
0x18000bd0f  jmp     short loc_18000BD13
0x18000bd11  xor     ecx, ecx
0x18000bd13  mov     edx, dword ptr [rsp+0B8h+var_58]
0x18000bd17  add     edx, ecx; uBytes
0x18000bd19  mov     ecx, 40h ; '@'; uFlags
0x18000bd1e  call    cs:__imp_LocalAlloc
0x18000bd25  nop     dword ptr [rax+rax+00h]
0x18000bd2a  mov     r14, rax
0x18000bd2d  test    rax, rax
0x18000bd30  jz      loc_18000BE17
0x18000bd36  mov     qword ptr [rax], 0
0x18000bd3d  mov     [rax+18h], ebx
0x18000bd40  mov     dword ptr [rax+1Ch], 1
0x18000bd47  mov     rax, [rsp+0B8h+Handle]
0x18000bd4f  mov     [r14+20h], rax
0x18000bd53  mov     eax, cs:dword_1800512F0
0x18000bd59  mov     [r14+28h], eax
0x18000bd5d  lea     ecx, [rax+1]
0x18000bd60  mov     eax, [rsp+0B8h+arg_40]
0x18000bd67  mov     [r14+38h], eax
0x18000bd6b  mov     rax, [rsp+0B8h+arg_48]
0x18000bd73  test    rax, rax
0x18000bd76  jz      short loc_18000BD80
0x18000bd78  movups  xmm0, xmmword ptr [rax]
0x18000bd7b  movups  xmmword ptr [r14+3Ch], xmm0
0x18000bd80  mov     rax, [rsp+0B8h+arg_50]
0x18000bd88  test    rax, rax
0x18000bd8b  jz      short loc_18000BD94
0x18000bd8d  mov     rax, [rax]
0x18000bd90  mov     [r14+4Ch], rax
0x18000bd94  mov     rax, [rsp+0B8h+arg_58]
0x18000bd9c  test    rax, rax
0x18000bd9f  jz      short loc_18000BDA8
0x18000bda1  mov     rax, [rax]
0x18000bda4  mov     [r14+54h], rax
0x18000bda8  btr     ecx, 1Fh
0x18000bdac  mov     cs:dword_1800512F0, ecx
0x18000bdb2  test    r13, r13
0x18000bdb5  jnz     loc_18000BB6C
0x18000bdbb  mov     [r14+10h], r13
0x18000bdbf  mov     [r14+30h], r13
0x18000bdc3  test    rdi, rdi
0x18000bdc6  jz      loc_18000BE51
0x18000bdcc  mov     ebp, [rsp+0B8h+arg_30]
0x18000bdd3  lea     edx, ds:12h[rbp*2]; uBytes
0x18000bdda  cmp     edx, 10h
0x18000bddd  jb      loc_18000BAA0
0x18000bde3  mov     eax, edx
0x18000bde5  shr     eax, 1
0x18000bde7  cmp     eax, ebp
0x18000bde9  jb      loc_18000BAA0
0x18000bdef  mov     ecx, 40h ; '@'; uFlags
0x18000bdf4  call    cs:__imp_LocalAlloc
0x18000bdfb  nop     dword ptr [rax+rax+00h]
0x18000be00  mov     rbx, rax
0x18000be03  test    rax, rax
0x18000be06  jnz     short loc_18000BE2E
0x18000be08  mov     rcx, r14; hMem
0x18000be0b  call    cs:__imp_LocalFree
0x18000be12  nop     dword ptr [rax+rax+00h]
0x18000be17  call    cs:__imp_GetLastError
0x18000be1e  nop     dword ptr [rax+rax+00h]
0x18000be23  mov     ebx, eax
0x18000be25  test    eax, eax
0x18000be27  jz      short loc_18000BE51
0x18000be29  jmp     loc_18000BAA5
0x18000be2e  lea     edx, [rbp+1]
0x18000be31  mov     r8, rdi
0x18000be34  lea     rcx, [rax+8]
0x18000be38  call    cs:__imp__o_wcscpy_s
0x18000be3f  nop     dword ptr [rax+rax+00h]
0x18000be44  mov     [rbx+4], ebp
0x18000be47  mov     dword ptr [rbx], 1
0x18000be4d  mov     [r14+8], rbx
0x18000be51  test    rsi, rsi
  ... truncated ...
```
