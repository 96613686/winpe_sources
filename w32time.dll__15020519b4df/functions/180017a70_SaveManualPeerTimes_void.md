# SaveManualPeerTimes(void)

- ea: `0x180017a70`
- end: `0x180017e7f`
- name: `?SaveManualPeerTimes@@YAJXZ`
- size: `1039`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18003748c`
- `0x180046a88`

## callees

- `0x180014774`
- `0x180015e20`
- `0x180016454`
- `0x1800164b0`
- `0x180017240`
- `0x1800179e4`
- `0x180017a70`
- `0x180018138`
- `0x18001d9a0`
- `0x18002fd6c`
- `0x18006c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x180017d28`
- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x180017d28`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180017b65`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180017b65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017da9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017da9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017afc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017afc`

## string_xrefs

- `0x180017d8f`: `WriteNtpClientSpecialPollTimeRemaining:0x%08x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 SaveManualPeerTimes(void)
{
  signed int MostRecentlySyncdDnsUniquePeers; // edi
  unsigned __int64 v1; // r15
  __int64 *v2; // rbx
  BYTE *v3; // rax
  BYTE *v4; // r13
  unsigned __int64 v5; // r14
  __int64 v6; // r12
  __int64 *i; // rbx
  unsigned int v8; // edx
  __int64 v9; // rsi
  __int64 v10; // rcx
  wchar_t *v11; // rax
  wchar_t *v12; // r10
  unsigned __int64 v13; // rcx
  _WORD *v14; // rax
  unsigned __int64 v15; // r8
  __int64 v16; // rcx
  __int16 *v17; // r9
  unsigned __int64 v18; // rdx
  _WORD *v19; // rax
  __int16 v20; // r8
  _WORD *v21; // rcx
  unsigned __int64 v22; // rcx
  _WORD *v23; // rax
  unsigned __int64 v24; // rax
  __int64 v25; // rcx
  const wchar_t *v26; // r9
  unsigned __int64 v27; // rdx
  wchar_t *v28; // r8
  wchar_t v29; // ax
  wchar_t *v30; // rcx
  __int64 v31; // rax
  unsigned __int64 v32; // r14
  wchar_t *v33; // rdi
  __int64 v34; // rcx
  unsigned int v35; // ebx
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v41; // [rsp+28h] [rbp-30h] BYREF
  __int64 *v42; // [rsp+30h] [rbp-28h] BYREF
  __int64 *v43; // [rsp+38h] [rbp-20h]

  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v42);
  v40 = 0;
  UpdatePeerListTimes();
  (*((void (__fastcall **)(__int64, __int64 *))g_pnpstate + 2))(3, &v40);
  v40 -= 10000000LL * *((unsigned int *)g_pnpstate + 47);
  MostRecentlySyncdDnsUniquePeers = GetMostRecentlySyncdDnsUniquePeers(&v42);
  if ( MostRecentlySyncdDnsUniquePeers >= 0 )
  {
    v1 = 1;
    v2 = v42;
    MostRecentlySyncdDnsUniquePeers = 0;
    while ( v2 != v43 )
    {
      v37 = *v2;
      if ( *v2 )
        _InterlockedIncrement((volatile signed __int32 *)v37);
      v38 = *(_QWORD *)(v37 + 8);
      if ( !*(_DWORD *)(v38 + 48) && (*(_DWORD *)(v38 + 80) & 1) != 0 )
      {
        v39 = -1;
        do
          ++v39;
        while ( *(_WORD *)(*(_QWORD *)(v38 + 72) + 2 * v39) );
        v1 += v39 + 15;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v37, 0xFFFFFFFF) == 1 )
        Ref<NtpPeer>::`scalar deleting destructor'((_QWORD *)v37, v38);
      ++v2;
    }
    v3 = (BYTE *)LocalAlloc(0x40u, 2 * v1);
    v4 = v3;
    if ( v3 )
    {
      if ( v1 > 0x7FFFFFFF )
      {
        MostRecentlySyncdDnsUniquePeers = -2147418113;
      }
      else
      {
        v5 = v1;
        v6 = (__int64)v3;
        for ( i = v42; ; ++i )
        {
          v8 = 44;
          if ( i == v43 )
            break;
          v9 = *i;
          v41 = (volatile signed __int32 *)v9;
          if ( v9 )
            _InterlockedIncrement((volatile signed __int32 *)v9);
          v10 = *(_QWORD *)(v9 + 8);
          if ( !*(_DWORD *)(v10 + 48) && (*(_DWORD *)(v10 + 80) & 1) != 0 )
          {
            v11 = wcschr(*(const wchar_t **)(v10 + 72), 0x2Cu);
            v12 = v11;
            if ( v11 )
              *v11 = 0;
            if ( !v5 )
            {
              MostRecentlySyncdDnsUniquePeers = -2147418113;
              goto LABEL_54;
            }
            if ( v5 > 0x7FFFFFFF )
            {
              MostRecentlySyncdDnsUniquePeers = -2147024809;
LABEL_54:
              AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(&v41);
              goto LABEL_55;
            }
            v13 = v5;
            v14 = (_WORD *)v6;
            do
            {
              if ( !*v14 )
                break;
              ++v14;
              --v13;
            }
            while ( v13 );
            MostRecentlySyncdDnsUniquePeers = v13 == 0 ? 0x80070057 : 0;
            if ( v13 )
              v15 = v5 - v13;
            else
              v15 = 0;
            if ( !v13 )
              goto LABEL_54;
            v16 = 2147483646;
            v17 = *(__int16 **)(*(_QWORD *)(v9 + 8) + 72LL);
            v18 = v5 - v15;
            v19 = (_WORD *)(v6 + 2 * v15);
            if ( v5 != v15 )
            {
              do
              {
                if ( !v16 )
                  break;
                v20 = *v17;
                if ( !*v17 )
                  break;
                ++v17;
                *v19++ = v20;
                --v16;
                --v18;
              }
              while ( v18 );
            }
            v21 = v19 - 1;
            if ( v18 )
              v21 = v19;
            *v21 = 0;
            MostRecentlySyncdDnsUniquePeers = v18 == 0 ? 0x8007007A : 0;
            if ( !v18 )
              goto LABEL_54;
            v22 = v5;
            v23 = (_WORD *)v6;
            do
            {
              if ( !*v23 )
                break;
              ++v23;
              --v22;
            }
            while ( v22 );
            MostRecentlySyncdDnsUniquePeers = v22 == 0 ? 0x80070057 : 0;
            v24 = v22 ? v5 - v22 : 0LL;
            if ( !v22 )
              goto LABEL_54;
            v25 = 2147483646;
            v26 = L",";
            v27 = v5 - v24;
            v28 = (wchar_t *)(v6 + 2 * v24);
            if ( v5 != v24 )
            {
              do
              {
                if ( !v25 )
                  break;
                v29 = *v26;
                if ( !*v26 )
                  break;
                ++v26;
                *v28++ = v29;
                --v25;
                --v27;
              }
              while ( v27 );
            }
            v30 = v28 - 1;
            if ( v27 )
              v30 = v28;
            *v30 = 0;
            MostRecentlySyncdDnsUniquePeers = v27 == 0 ? 0x8007007A : 0;
            if ( !v27 )
              goto LABEL_54;
            v31 = -1;
            do
              ++v31;
            while ( *(_WORD *)(v6 + 2 * v31) );
            v32 = v5 - v31;
            v33 = (wchar_t *)(v6 + 2 * v31);
            if ( v12 )
              *v12 = 44;
            _ultow(*(_QWORD *)(*(_QWORD *)(v9 + 8) + 832LL) / 0x3B9ACA00uLL, v33, 16);
            v34 = -1;
            do
              ++v34;
            while ( v33[v34] );
            v5 = -1 - v34 + v32;
            v6 = (__int64)&v33[v34 + 1];
            MostRecentlySyncdDnsUniquePeers = 0;
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9, 0xFFFFFFFF) == 1 )
          {
            if ( v9 )
              Ref<NtpPeer>::`scalar deleting destructor'((_QWORD *)v9, v8);
          }
        }
        v35 = WriteNtpClientSpecialPollTimeRemaining(v4, v1);
        if ( v35 && (unsigned __int8)FileLogAllowEntry(0) )
          FileLogAdd(L"WriteNtpClientSpecialPollTimeRemaining:0x%08x\n", v35);
      }
LABEL_55:
      LocalFree(v4);
    }
    else
    {
      MostRecentlySyncdDnsUniquePeers = -2147024882;
    }
  }
  std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::~vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>((__int64)&v42);
  return (unsigned int)MostRecentlySyncdDnsUniquePeers;
}

```

## disassembly

```asm
0x180017a70  push    rbp
0x180017a72  push    rbx
0x180017a73  push    rsi
0x180017a74  push    rdi
0x180017a75  push    r12
0x180017a77  push    r13
0x180017a79  push    r14
0x180017a7b  push    r15
0x180017a7d  mov     rbp, rsp
0x180017a80  sub     rsp, 58h
0x180017a84  lea     rcx, [rbp+var_28]
0x180017a88  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180017a8d  nop
0x180017a8e  xor     r12d, r12d
0x180017a91  mov     [rbp+var_38], r12
0x180017a95  call    ?UpdatePeerListTimes@@YAXXZ; UpdatePeerListTimes(void)
0x180017a9a  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180017aa1  lea     rdx, [rbp+var_38]
0x180017aa5  lea     ecx, [r12+3]
0x180017aaa  mov     rax, [rax+10h]
0x180017aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ab3  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180017aba  mov     ecx, [rax+0BCh]
0x180017ac0  imul    rax, rcx, 989680h
0x180017ac7  sub     [rbp+var_38], rax
0x180017acb  lea     rcx, [rbp+var_28]
0x180017acf  call    ?GetMostRecentlySyncdDnsUniquePeers@@YAJAEAV?$vector@V?$AutoPtr@UNtpPeer@@@@V?$MyThrowingAllocator@V?$AutoPtr@UNtpPeer@@@@@@@std@@@Z; GetMostRecentlySyncdDnsUniquePeers(std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>> &)
0x180017ad4  mov     edi, eax
0x180017ad6  test    eax, eax
0x180017ad8  js      loc_180017DB6
0x180017ade  lea     r15d, [r12+1]
0x180017ae3  mov     rbx, [rbp+var_28]
0x180017ae7  xor     edi, edi
0x180017ae9  cmp     rbx, [rbp+var_20]
0x180017aed  jnz     loc_180017DD3
0x180017af3  lea     rdx, [r15+r15]; uBytes
0x180017af7  mov     ecx, 40h ; '@'; uFlags
0x180017afc  call    cs:__imp_LocalAlloc
0x180017b03  nop     dword ptr [rax+rax+00h]
0x180017b08  mov     r13, rax
0x180017b0b  test    rax, rax
0x180017b0e  jz      loc_180017E3D
0x180017b14  cmp     r15, 7FFFFFFFh
0x180017b1b  ja      loc_180017E47
0x180017b21  mov     r14, r15
0x180017b24  mov     r12, rax
0x180017b27  mov     rbx, [rbp+var_28]
0x180017b2b  mov     edx, 2Ch ; ','; Ch
0x180017b30  cmp     rbx, [rbp+var_20]
0x180017b34  jz      loc_180017D71
0x180017b3a  mov     rsi, [rbx]
0x180017b3d  mov     [rbp+var_30], rsi
0x180017b41  test    rsi, rsi
0x180017b44  jz      short loc_180017B49
0x180017b46  lock inc dword ptr [rsi]
0x180017b49  mov     rcx, [rsi+8]
0x180017b4d  cmp     [rcx+30h], edi
0x180017b50  jnz     loc_180017D58
0x180017b56  mov     eax, [rcx+50h]
0x180017b59  test    al, 1
0x180017b5b  jz      loc_180017D58
0x180017b61  mov     rcx, [rcx+48h]; Str
0x180017b65  call    cs:__imp_wcschr
0x180017b6c  nop     dword ptr [rax+rax+00h]
0x180017b71  mov     r10, rax
0x180017b74  xor     r11d, r11d
0x180017b77  test    rax, rax
0x180017b7a  jnz     loc_180017E51
0x180017b80  test    r14, r14
0x180017b83  jz      loc_180017E74
0x180017b89  cmp     r14, 7FFFFFFFh
0x180017b90  ja      loc_180017E6A
0x180017b96  mov     rcx, r14
0x180017b99  mov     rax, r12
0x180017b9c  cmp     [rax], r11w
0x180017ba0  jz      short loc_180017BAC
0x180017ba2  add     rax, 2
0x180017ba6  sub     rcx, 1
0x180017baa  jnz     short loc_180017B9C
0x180017bac  mov     rax, rcx
0x180017baf  neg     rax
0x180017bb2  sbb     edi, edi
0x180017bb4  not     edi
0x180017bb6  and     edi, 80070057h
0x180017bbc  test    rcx, rcx
0x180017bbf  jz      loc_180017E5A
0x180017bc5  mov     r8, r14
0x180017bc8  sub     r8, rcx
0x180017bcb  test    rcx, rcx
0x180017bce  jz      loc_180017D9D
0x180017bd4  mov     ecx, 7FFFFFFEh
0x180017bd9  mov     rax, [rsi+8]
0x180017bdd  mov     r9, [rax+48h]
0x180017be1  mov     rdx, r14
0x180017be4  sub     rdx, r8
0x180017be7  lea     rax, [r12+r8*2]
0x180017beb  jz      short loc_180017C11
0x180017bed  test    rcx, rcx
0x180017bf0  jz      short loc_180017C11
0x180017bf2  movzx   r8d, word ptr [r9]
0x180017bf6  test    r8w, r8w
0x180017bfa  jz      short loc_180017C11
0x180017bfc  add     r9, 2
0x180017c00  mov     [rax], r8w
0x180017c04  add     rax, 2
0x180017c08  dec     rcx
0x180017c0b  sub     rdx, 1
0x180017c0f  jnz     short loc_180017BED
0x180017c11  lea     rcx, [rax-2]
0x180017c15  test    rdx, rdx
0x180017c18  cmovnz  rcx, rax
0x180017c1c  mov     [rcx], r11w
0x180017c20  mov     rax, rdx
0x180017c23  neg     rax
0x180017c26  sbb     edi, edi
0x180017c28  not     edi
0x180017c2a  and     edi, 8007007Ah
0x180017c30  test    rdx, rdx
0x180017c33  jz      loc_180017D9D
0x180017c39  mov     rcx, r14
0x180017c3c  mov     rax, r12
0x180017c3f  cmp     [rax], r11w
0x180017c43  jz      short loc_180017C4F
0x180017c45  add     rax, 2
0x180017c49  sub     rcx, 1
0x180017c4d  jnz     short loc_180017C3F
0x180017c4f  mov     rax, rcx
0x180017c52  neg     rax
0x180017c55  sbb     edi, edi
0x180017c57  not     edi
0x180017c59  and     edi, 80070057h
0x180017c5f  test    rcx, rcx
0x180017c62  jz      loc_180017E62
0x180017c68  mov     rax, r14
0x180017c6b  sub     rax, rcx
0x180017c6e  test    rcx, rcx
0x180017c71  jz      loc_180017D9D
0x180017c77  mov     ecx, 7FFFFFFEh
0x180017c7c  lea     r9, asc_180072194; ","
0x180017c83  mov     rdx, r14
0x180017c86  sub     rdx, rax
0x180017c89  lea     r8, [r12+rax*2]
0x180017c8d  jz      short loc_180017CB2
0x180017c8f  test    rcx, rcx
0x180017c92  jz      short loc_180017CB2
0x180017c94  movzx   eax, word ptr [r9]
0x180017c98  test    ax, ax
0x180017c9b  jz      short loc_180017CB2
0x180017c9d  add     r9, 2
0x180017ca1  mov     [r8], ax
0x180017ca5  add     r8, 2
0x180017ca9  dec     rcx
0x180017cac  sub     rdx, 1
0x180017cb0  jnz     short loc_180017C8F
0x180017cb2  lea     rcx, [r8-2]
0x180017cb6  test    rdx, rdx
0x180017cb9  cmovnz  rcx, r8
0x180017cbd  mov     [rcx], r11w
0x180017cc1  mov     rax, rdx
0x180017cc4  neg     rax
0x180017cc7  sbb     edi, edi
0x180017cc9  not     edi
0x180017ccb  and     edi, 8007007Ah
0x180017cd1  test    rdx, rdx
0x180017cd4  jz      loc_180017D9D
0x180017cda  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017cde  inc     rax
0x180017ce1  cmp     [r12+rax*2], r11w
0x180017ce6  jnz     short loc_180017CDE
0x180017ce8  sub     r14, rax
0x180017ceb  lea     rdi, [r12+rax*2]
0x180017cef  test    r10, r10
0x180017cf2  jz      short loc_180017CFA
0x180017cf4  mov     word ptr [r10], 2Ch ; ','
0x180017cfa  mov     rax, [rsi+8]
0x180017cfe  mov     rcx, [rax+340h]
0x180017d05  mov     rax, 12E0BE826D694B2Fh
0x180017d0f  mul     rcx
0x180017d12  sub     rcx, rdx
0x180017d15  shr     rcx, 1
0x180017d18  add     rcx, rdx
0x180017d1b  shr     rcx, 1Dh; Value
0x180017d1f  mov     r8d, 10h; Radix
0x180017d25  mov     rdx, rdi; Buffer
0x180017d28  call    cs:__imp__ultow
0x180017d2f  nop     dword ptr [rax+rax+00h]
0x180017d34  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017d38  mov     rcx, rax
0x180017d3b  xor     r12d, r12d
0x180017d3e  inc     rcx
0x180017d41  cmp     [rdi+rcx*2], r12w
0x180017d46  jnz     short loc_180017D3E
0x180017d48  sub     rax, rcx
0x180017d4b  add     r14, rax
0x180017d4e  lea     r12, [rdi+2]
0x180017d52  lea     r12, [r12+rcx*2]
0x180017d56  xor     edi, edi
0x180017d58  or      eax, 0FFFFFFFFh
0x180017d5b  lock xadd [rsi], eax
0x180017d5f  cmp     eax, 1
0x180017d62  jz      loc_180017E20
0x180017d68  add     rbx, 8
0x180017d6c  jmp     loc_180017B2B
0x180017d71  mov     rdx, r15
0x180017d74  mov     rcx, r13; lpData
0x180017d77  call    WriteNtpClientSpecialPollTimeRemaining
0x180017d7c  mov     ebx, eax
0x180017d7e  test    eax, eax
0x180017d80  jz      short loc_180017DA6
0x180017d82  xor     ecx, ecx
0x180017d84  call    FileLogAllowEntry
0x180017d89  test    al, al
0x180017d8b  jz      short loc_180017DA6
0x180017d8d  mov     edx, ebx
0x180017d8f  lea     rcx, aWritentpclient_0; "WriteNtpClientSpecialPollTimeRemaining:"...
0x180017d96  call    FileLogAdd
0x180017d9b  jmp     short loc_180017DA6
0x180017d9d  lea     rcx, [rbp+var_30]
0x180017da1  call    ??1?$AutoPtr@UNtpPeer@@@@QEAA@XZ; AutoPtr<NtpPeer>::~AutoPtr<NtpPeer>(void)
0x180017da6  mov     rcx, r13; hMem
0x180017da9  call    cs:__imp_LocalFree
0x180017db0  nop     dword ptr [rax+rax+00h]
0x180017db5  nop
0x180017db6  lea     rcx, [rbp+var_28]
0x180017dba  call    ??1?$vector@V?$AutoPtr@UNtpPeer@@@@V?$MyThrowingAllocator@V?$AutoPtr@UNtpPeer@@@@@@@std@@QEAA@XZ; std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::~vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>(void)
0x180017dbf  mov     eax, edi
0x180017dc1  add     rsp, 58h
0x180017dc5  pop     r15
0x180017dc7  pop     r14
0x180017dc9  pop     r13
0x180017dcb  pop     r12
0x180017dcd  pop     rdi
0x180017dce  pop     rsi
0x180017dcf  pop     rbx
0x180017dd0  pop     rbp
0x180017dd1  retn
0x180017dd3  mov     rcx, [rbx]; void *
0x180017dd6  mov     [rbp+arg_0], rcx
0x180017dda  test    rcx, rcx
0x180017ddd  jz      short loc_180017DE2
0x180017ddf  lock inc dword ptr [rcx]
0x180017de2  mov     rdx, [rcx+8]
0x180017de6  cmp     [rdx+30h], edi
0x180017de9  jnz     short loc_180017E0B
0x180017deb  mov     eax, [rdx+50h]
0x180017dee  test    al, 1
0x180017df0  jz      short loc_180017E0B
0x180017df2  mov     r8, [rdx+48h]
0x180017df6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017dfa  inc     rax
0x180017dfd  cmp     [r8+rax*2], di
0x180017e02  jnz     short loc_180017DFA
0x180017e04  add     r15, 0Fh
0x180017e08  add     r15, rax
0x180017e0b  or      eax, 0FFFFFFFFh
0x180017e0e  lock xadd [rcx], eax
0x180017e12  cmp     eax, 1
0x180017e15  jz      short loc_180017E36
0x180017e17  add     rbx, 8
0x180017e1b  jmp     loc_180017AE9
0x180017e20  test    rsi, rsi
0x180017e23  jz      loc_180017D68
0x180017e29  mov     rcx, rsi; void *
0x180017e2c  call    ??_G?$Ref@UNtpPeer@@@@QEAAPEAXI@Z; Ref<NtpPeer>::`scalar deleting destructor'(uint)
0x180017e31  jmp     loc_180017D68
0x180017e36  call    ??_G?$Ref@UNtpPeer@@@@QEAAPEAXI@Z; Ref<NtpPeer>::`scalar deleting destructor'(uint)
0x180017e3b  jmp     short loc_180017E17
0x180017e3d  mov     edi, 8007000Eh
0x180017e42  jmp     loc_180017DB6
0x180017e47  mov     edi, 8000FFFFh
0x180017e4c  jmp     loc_180017DA6
0x180017e51  mov     [rax], r11w
0x180017e55  jmp     loc_180017B80
0x180017e5a  mov     r8, r11
0x180017e5d  jmp     loc_180017BCB
0x180017e62  mov     rax, r11
0x180017e65  jmp     loc_180017C6E
0x180017e6a  mov     edi, 80070057h
0x180017e6f  jmp     loc_180017D9D
0x180017e74  mov     edi, 8000FFFFh
0x180017e79  jmp     loc_180017D9D
```
