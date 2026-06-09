# WsAddUse

- ea: `0x18000af60`
- end: `0x18000b467`
- name: `WsAddUse`
- size: `1287`
- prototype: `__int64 __fastcall(PLUID SourceLuid, PLUID, void *, __int64, unsigned int, WCHAR *, unsigned int, __int64, int, _OWORD *, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001710`
- `0x1800299a4`

## callees

- `0x18000abb0`
- `0x18000af60`
- `0x180010b48`
- `0x18002ef08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000b1ad`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000b1de`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000b42d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000b1ad`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000b1de`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000b42d`
- `ntdll!RtlCopyLuid` at `0x18000b23f`
- `ntdll!RtlCopyLuid` at `0x18000b256`
- `ntdll!RtlCopyLuid` at `0x18000b23f`
- `ntdll!RtlCopyLuid` at `0x18000b256`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000af8b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000af8b`
- `ntdll!NtClose` at `0x18000b17b`
- `ntdll!NtClose` at `0x18000b17b`
- `ntdll!RtlReleaseResource` at `0x18000b0ee`
- `ntdll!RtlReleaseResource` at `0x18000b16d`
- `ntdll!RtlReleaseResource` at `0x18000b211`
- `ntdll!RtlReleaseResource` at `0x18000b45c`
- `ntdll!RtlReleaseResource` at `0x18000b0ee`
- `ntdll!RtlReleaseResource` at `0x18000b16d`
- `ntdll!RtlReleaseResource` at `0x18000b211`
- `ntdll!RtlReleaseResource` at `0x18000b45c`
- `ntdll!RtlCompareUnicodeString` at `0x18000b0b1`
- `ntdll!RtlCompareUnicodeString` at `0x18000b0b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b412`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b32f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b3fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b32f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b3fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b40c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b40c`

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
  while ( (unsigned int)v17 < dword_18004F110 )
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
      v37 = dword_18004E2F0;
      *((_DWORD *)v34 + 10) = dword_18004E2F0;
      *((_DWORD *)v34 + 14) = a9;
      if ( a10 )
        *(_OWORD *)(v34 + 60) = *a10;
      if ( a11 )
        *(_QWORD *)(v34 + 76) = *a11;
      if ( a12 )
        *(_QWORD *)(v34 + 84) = *a12;
      dword_18004E2F0 = (v37 + 1) & 0x7FFFFFFF;
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
  v32 = WsGrowTable(&Use, LowPart, (unsigned int)dword_18004F110, Use);
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
0x18000af60  mov     [rsp+Handle], r8
0x18000af65  push    rbp
0x18000af66  push    rsi
0x18000af67  push    r13
0x18000af69  sub     rsp, 0A0h
0x18000af70  mov     rbp, rdx
0x18000af73  mov     [rsp+0B8h+var_58], 0
0x18000af7c  mov     rsi, rcx
0x18000af7f  mov     dl, 1; Wait
0x18000af81  lea     rcx, Resource; Resource
0x18000af88  mov     r13, r9
0x18000af8b  call    cs:__imp_RtlAcquireResourceExclusive
0x18000af91  test    al, al
0x18000af93  jz      loc_18000B1E9
0x18000af99  mov     r8d, cs:dword_18004F110
0x18000afa0  mov     r9, cs:Use
0x18000afa7  mov     [rsp+0B8h+arg_0], rbx
0x18000afaf  xor     ebx, ebx
0x18000afb1  mov     [rsp+0B8h+arg_8], rdi
0x18000afb9  mov     edi, 0FFFFFFFFh
0x18000afbe  xchg    ax, ax
0x18000afc0  cmp     ebx, r8d
0x18000afc3  jnb     loc_18000B1F3
0x18000afc9  mov     edx, [rsi]
0x18000afcb  lea     rcx, [rbx+rbx*2]
0x18000afcf  cmp     edx, [r9+rcx*8+8]
0x18000afd4  jz      short loc_18000AFEE
0x18000afd6  cmp     edx, [r9+rcx*8+10h]
0x18000afdb  jz      loc_18000B188
0x18000afe1  cmp     edi, 0FFFFFFFFh
0x18000afe4  jz      loc_18000B12A
0x18000afea  inc     ebx
0x18000afec  jmp     short loc_18000AFC0
0x18000afee  mov     eax, [r9+rcx*8+0Ch]
0x18000aff3  cmp     [rsi+4], eax
0x18000aff6  jnz     short loc_18000AFD6
0x18000aff8  mov     rdi, [rsp+0B8h+arg_28]
0x18000b000  xor     esi, esi
0x18000b002  mov     [rsp+0B8h+arg_18], r12
0x18000b00a  mov     eax, ebx
0x18000b00c  mov     [rsp+0B8h+var_20], r14
0x18000b014  mov     [rsp+0B8h+var_28], r15
0x18000b01c  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18000b023  lea     rcx, [rax+rax*2]
0x18000b027  lea     r12, ds:0[rcx*8]
0x18000b02f  mov     rbx, [r12+r9]
0x18000b033  test    rbx, rbx
0x18000b036  jz      loc_18000B0CF
0x18000b03c  xor     ebp, ebp
0x18000b03e  xor     r14d, r14d
0x18000b041  test    ebp, ebp
0x18000b043  jnz     short loc_18000B0BB
0x18000b045  mov     rcx, [rbx+8]
0x18000b049  xorps   xmm0, xmm0
0x18000b04c  xorps   xmm1, xmm1
0x18000b04f  add     rcx, 8
0x18000b053  movups  xmmword ptr [rsp+0B8h+String1.Length], xmm0
0x18000b058  mov     rax, r15
0x18000b05b  movups  xmmword ptr [rsp+0B8h+String2.Length], xmm1
0x18000b060  inc     rax
0x18000b063  cmp     word ptr [rcx+rax*2], 0
0x18000b068  jnz     short loc_18000B060
0x18000b06a  inc     ax
0x18000b06d  mov     [rsp+0B8h+String1.Buffer], rcx
0x18000b075  add     ax, ax
0x18000b078  mov     [rsp+0B8h+String1.MaximumLength], ax
0x18000b07d  mov     [rsp+0B8h+String1.Length], ax
0x18000b082  mov     rax, r15
0x18000b085  inc     rax
0x18000b088  cmp     word ptr [rdi+rax*2], 0
0x18000b08d  jnz     short loc_18000B085
0x18000b08f  inc     ax
0x18000b092  mov     [rsp+0B8h+String2.Buffer], rdi
0x18000b097  add     ax, ax
0x18000b09a  lea     rdx, [rsp+0B8h+String2]; String2
0x18000b09f  mov     r8b, 1; CaseInsensitive
0x18000b0a2  mov     [rsp+0B8h+String2.MaximumLength], ax
0x18000b0a7  lea     rcx, [rsp+0B8h+String1]; String1
0x18000b0ac  mov     [rsp+0B8h+String2.Length], ax
0x18000b0b1  call    cs:__imp_RtlCompareUnicodeString
0x18000b0b7  test    eax, eax
0x18000b0b9  jz      short loc_18000B137
0x18000b0bb  mov     rsi, rbx
0x18000b0be  mov     rbx, [rbx]
0x18000b0c1  test    rbx, rbx
0x18000b0c4  jnz     loc_18000B041
0x18000b0ca  test    r14, r14
0x18000b0cd  jnz     short loc_18000B149
0x18000b0cf  mov     ebx, [rsp+0B8h+arg_20]
0x18000b0d6  cmp     ebx, 0FFFFh
0x18000b0dc  jbe     loc_18000B2F5
0x18000b0e2  mov     ebx, 90Dh
0x18000b0e7  lea     rcx, Resource; Resource
0x18000b0ee  call    cs:__imp_RtlReleaseResource
0x18000b0f4  mov     eax, ebx
0x18000b0f6  mov     r14, [rsp+0B8h+var_20]
0x18000b0fe  mov     r12, [rsp+0B8h+arg_18]
0x18000b106  mov     r15, [rsp+0B8h+var_28]
0x18000b10e  mov     rbx, [rsp+0B8h+arg_0]
0x18000b116  mov     rdi, [rsp+0B8h+arg_8]
0x18000b11e  add     rsp, 0A0h
0x18000b125  pop     r13
0x18000b127  pop     rsi
0x18000b128  pop     rbp
0x18000b129  retn
0x18000b12a  cmp     qword ptr [r9+rcx*8], 0
0x18000b12f  cmovz   edi, ebx
0x18000b132  jmp     loc_18000AFEA
0x18000b137  xor     ebp, ebp
0x18000b139  mov     r14, rbx
0x18000b13c  cmp     [rbx+10h], rbp
0x18000b140  setz    bpl
0x18000b144  jmp     loc_18000B0BB
0x18000b149  test    r13, r13
0x18000b14c  jnz     loc_18000B26A
0x18000b152  cmp     [r14+10h], r13
0x18000b156  jnz     loc_18000B26A
0x18000b15c  mov     rax, [r14+8]
0x18000b160  lea     rcx, Resource; Resource
0x18000b167  inc     dword ptr [r14+1Ch]
0x18000b16b  inc     dword ptr [rax]
0x18000b16d  call    cs:__imp_RtlReleaseResource
0x18000b173  mov     rcx, [rsp+0B8h+Handle]; Handle
0x18000b17b  call    cs:__imp_NtClose
0x18000b181  xor     eax, eax
0x18000b183  jmp     loc_18000B0F6
0x18000b188  mov     eax, [r9+rcx*8+14h]
0x18000b18d  cmp     [rsi+4], eax
0x18000b190  jnz     loc_18000AFE1
0x18000b196  jmp     loc_18000AFF8
0x18000b19b  lea     eax, [rbx+1]
0x18000b19e  mov     r8, r13
0x18000b1a1  lea     rcx, [r14+60h]
0x18000b1a5  mov     edx, eax
0x18000b1a7  mov     [r14+10h], rcx
0x18000b1ab  mov     ebx, eax
0x18000b1ad  call    cs:__imp__o_wcscpy_s
0x18000b1b3  lea     rcx, [rbx+30h]
0x18000b1b7  lea     rcx, [r14+rcx*2]
0x18000b1bb  lea     rax, [rcx+2]
0x18000b1bf  cmp     rax, rcx
0x18000b1c2  jbe     short loc_18000B1CC
0x18000b1c4  lea     r15, [rcx+1]
0x18000b1c8  and     r15, 0FFFFFFFFFFFFFFFEh
0x18000b1cc  mov     [r14+30h], r15
0x18000b1d0  mov     rcx, r15
0x18000b1d3  movzx   edx, word ptr [rbp+2]
0x18000b1d7  mov     r8, [rbp+8]
0x18000b1db  shr     rdx, 1
0x18000b1de  call    cs:__imp__o_wcscpy_s
0x18000b1e4  jmp     loc_18000B3CE
0x18000b1e9  mov     eax, 85Ch
0x18000b1ee  jmp     loc_18000B11E
0x18000b1f3  cmp     edi, 0FFFFFFFFh
0x18000b1f6  jnz     short loc_18000B227
0x18000b1f8  lea     rcx, Use
0x18000b1ff  call    WsGrowTable
0x18000b204  mov     edi, eax
0x18000b206  test    eax, eax
0x18000b208  jz      short loc_18000B21E
0x18000b20a  lea     rcx, Resource; Resource
0x18000b211  call    cs:__imp_RtlReleaseResource
0x18000b217  mov     eax, edi
0x18000b219  jmp     loc_18000B10E
0x18000b21e  mov     r9, cs:Use
0x18000b225  mov     edi, ebx
0x18000b227  mov     eax, edi
0x18000b229  mov     rdx, rsi; SourceLuid
0x18000b22c  lea     rcx, [rax+rax*2]
0x18000b230  lea     rbx, ds:0[rcx*8]
0x18000b238  lea     rcx, [r9+8]
0x18000b23c  add     rcx, rbx; DestinationLuid
0x18000b23f  call    cs:__imp_RtlCopyLuid
0x18000b245  mov     rcx, cs:Use
0x18000b24c  mov     rdx, rbp; SourceLuid
0x18000b24f  add     rcx, 10h
0x18000b253  add     rcx, rbx; DestinationLuid
0x18000b256  call    cs:__imp_RtlCopyLuid
0x18000b25c  mov     r9, cs:Use
0x18000b263  mov     ebx, edi
0x18000b265  jmp     loc_18000AFF8
0x18000b26a  mov     rax, [rsp+0B8h+arg_58]
0x18000b272  lea     rcx, [rsp+0B8h+var_58]
0x18000b277  mov     r9d, [rsp+0B8h+arg_20]
0x18000b27f  mov     r8, r13
0x18000b282  mov     rdx, [rsp+0B8h+Handle]
0x18000b28a  mov     [rsp+0B8h+var_68], rax
0x18000b28f  mov     rax, [rsp+0B8h+arg_50]
0x18000b297  mov     [rsp+0B8h+var_70], rax
0x18000b29c  mov     rax, [rsp+0B8h+arg_48]
0x18000b2a4  mov     [rsp+0B8h+var_78], rax
0x18000b2a9  mov     eax, [rsp+0B8h+arg_40]
0x18000b2b0  mov     [rsp+0B8h+var_80], eax
0x18000b2b4  mov     rax, [rsp+0B8h+arg_38]
0x18000b2bc  mov     [rsp+0B8h+var_88], rax
0x18000b2c1  mov     [rsp+0B8h+var_90], 0
0x18000b2c9  mov     [rsp+0B8h+var_98], 0
0x18000b2d2  call    WsCreateNewEntry
0x18000b2d7  mov     ebx, eax
0x18000b2d9  test    eax, eax
0x18000b2db  jnz     loc_18000B0E7
0x18000b2e1  mov     rax, [r14+8]
0x18000b2e5  mov     r14, [rsp+0B8h+var_58]
0x18000b2ea  mov     [r14+8], rax
0x18000b2ee  inc     dword ptr [rax]
0x18000b2f0  jmp     loc_18000B440
0x18000b2f5  lea     ecx, ds:62h[rbx*2]
0x18000b2fc  mov     edx, 2
0x18000b301  lea     r8, [rsp+0B8h+var_58]
0x18000b306  mov     dword ptr [rsp+0B8h+var_58], ecx
0x18000b30a  call    NetpULongRoundUp
0x18000b30f  mov     rbp, [rsp+0B8h+arg_38]
0x18000b317  test    r13, r13
0x18000b31a  jz      short loc_18000B322
0x18000b31c  movzx   ecx, word ptr [rbp+2]
0x18000b320  jmp     short loc_18000B324
0x18000b322  xor     ecx, ecx
0x18000b324  mov     edx, dword ptr [rsp+0B8h+var_58]
0x18000b328  add     edx, ecx; uBytes
0x18000b32a  mov     ecx, 40h ; '@'; uFlags
0x18000b32f  call    cs:__imp_LocalAlloc
0x18000b335  mov     r14, rax
0x18000b338  test    rax, rax
0x18000b33b  jz      loc_18000B412
0x18000b341  mov     qword ptr [rax], 0
0x18000b348  mov     [rax+18h], ebx
0x18000b34b  mov     dword ptr [rax+1Ch], 1
0x18000b352  mov     rax, [rsp+0B8h+Handle]
0x18000b35a  mov     [r14+20h], rax
0x18000b35e  mov     eax, cs:dword_18004E2F0
0x18000b364  mov     [r14+28h], eax
0x18000b368  lea     ecx, [rax+1]
0x18000b36b  mov     eax, [rsp+0B8h+arg_40]
0x18000b372  mov     [r14+38h], eax
0x18000b376  mov     rax, [rsp+0B8h+arg_48]
0x18000b37e  test    rax, rax
0x18000b381  jz      short loc_18000B38B
0x18000b383  movups  xmm0, xmmword ptr [rax]
0x18000b386  movups  xmmword ptr [r14+3Ch], xmm0
0x18000b38b  mov     rax, [rsp+0B8h+arg_50]
0x18000b393  test    rax, rax
0x18000b396  jz      short loc_18000B39F
0x18000b398  mov     rax, [rax]
0x18000b39b  mov     [r14+4Ch], rax
0x18000b39f  mov     rax, [rsp+0B8h+arg_58]
0x18000b3a7  test    rax, rax
0x18000b3aa  jz      short loc_18000B3B3
0x18000b3ac  mov     rax, [rax]
0x18000b3af  mov     [r14+54h], rax
0x18000b3b3  btr     ecx, 1Fh
0x18000b3b7  mov     cs:dword_18004E2F0, ecx
0x18000b3bd  test    r13, r13
0x18000b3c0  jnz     loc_18000B19B
0x18000b3c6  mov     [r14+10h], r13
0x18000b3ca  mov     [r14+30h], r13
0x18000b3ce  test    rdi, rdi
0x18000b3d1  jz      short loc_18000B440
0x18000b3d3  mov     ebp, [rsp+0B8h+arg_30]
0x18000b3da  lea     edx, ds:12h[rbp*2]; uBytes
0x18000b3e1  cmp     edx, 10h
0x18000b3e4  jb      loc_18000B0E2
0x18000b3ea  mov     eax, edx
0x18000b3ec  shr     eax, 1
0x18000b3ee  cmp     eax, ebp
0x18000b3f0  jb      loc_18000B0E2
0x18000b3f6  mov     ecx, 40h ; '@'; uFlags
0x18000b3fb  call    cs:__imp_LocalAlloc
0x18000b401  mov     rbx, rax
0x18000b404  test    rax, rax
0x18000b407  jnz     short loc_18000B423
0x18000b409  mov     rcx, r14; hMem
0x18000b40c  call    cs:__imp_LocalFree
0x18000b412  call    cs:__imp_GetLastError
0x18000b418  mov     ebx, eax
0x18000b41a  test    eax, eax
0x18000b41c  jz      short loc_18000B440
0x18000b41e  jmp     loc_18000B0E7
0x18000b423  lea     edx, [rbp+1]
0x18000b426  mov     r8, rdi
0x18000b429  lea     rcx, [rax+8]
0x18000b42d  call    cs:__imp__o_wcscpy_s
0x18000b433  mov     [rbx+4], ebp
0x18000b436  mov     dword ptr [rbx], 1
0x18000b43c  mov     [r14+8], rbx
0x18000b440  test    rsi, rsi
0x18000b443  jnz     short loc_18000B452
0x18000b445  mov     rax, cs:Use
0x18000b44c  mov     [r12+rax], r14
0x18000b450  jmp     short loc_18000B455
0x18000b452  mov     [rsi], r14
0x18000b455  lea     rcx, Resource; Resource
0x18000b45c  call    cs:__imp_RtlReleaseResource
0x18000b462  jmp     loc_18000B181
```
