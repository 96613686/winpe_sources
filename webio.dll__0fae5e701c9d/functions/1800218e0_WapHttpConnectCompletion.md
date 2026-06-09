# WapHttpConnectCompletion

- ea: `0x1800218e0`
- end: `0x180021d86`
- name: `WapHttpConnectCompletion`
- size: `1190`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180022118`

## callees

- `0x180013284`
- `0x18001b150`
- `0x1800204f0`
- `0x1800218e0`
- `0x180021e84`
- `0x180022064`
- `0x180033fe4`
- `0x180035f30`
- `0x180036958`
- `0x180037590`
- `0x180045398`
- `0x180059ae0`
- `0x180061cb8`
- `0x180062530`
- `0x180066680`
- `0x1800682e0`
- `0x1800722f0`
- `0x180080e64`
- `0x1800951fc`
- `0x180097374`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021957`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021957`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800219f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800219f8`

## pseudocode

```c
__int64 __fastcall WapHttpConnectCompletion(__int64 a1, unsigned int a2, int a3)
{
  __int64 v5; // rcx
  volatile signed __int32 *v6; // rdi
  char v7; // r14
  char v8; // r12
  char v9; // r15
  bool v10; // si
  volatile signed __int32 *v11; // rax
  volatile signed __int32 *v12; // r13
  char v13; // r11
  int v14; // edx
  int v15; // ecx
  int v16; // r8d
  int v17; // edi
  _QWORD *v18; // rax
  volatile signed __int32 *v19; // rcx
  __int64 result; // rax
  __int64 v21; // rcx
  _QWORD *v22; // rdx
  volatile signed __int32 *v23; // rsi
  char v24; // dl
  unsigned int v25; // ecx
  unsigned int v26; // edx
  bool v27; // [rsp+40h] [rbp-29h]
  unsigned int v28; // [rsp+44h] [rbp-25h]
  char v29; // [rsp+48h] [rbp-21h]
  volatile signed __int32 *lpMem; // [rsp+50h] [rbp-19h]
  volatile signed __int32 *v31; // [rsp+58h] [rbp-11h]
  int v32; // [rsp+60h] [rbp-9h] BYREF
  _QWORD v33[3]; // [rsp+68h] [rbp-1h] BYREF

  v28 = a2;
  v33[1] = v33;
  v32 = 0;
  v33[0] = v33;
  v5 = *(_QWORD *)(a1 + 64);
  v6 = 0;
  v33[2] = 0;
  v7 = 0;
  v29 = 0;
  v8 = 0;
  v27 = 0;
  v9 = *(_BYTE *)(v5 + 144);
  v10 = 0;
  if ( !a2 )
  {
    if ( *(_BYTE *)(a1 + 106) )
    {
      v8 = 1;
    }
    else if ( *(_BYTE *)(a1 + 110)
           && !(*(unsigned int (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)(a1 + 72) + 72LL))(v5, 19, &v32) )
    {
      v10 = (v32 & 1) != 0;
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  lpMem = *(volatile signed __int32 **)(a1 + 232);
  v11 = *(volatile signed __int32 **)(a1 + 240);
  *(_DWORD *)(a1 + 56) = a3;
  v12 = *(volatile signed __int32 **)(a1 + 248);
  *(_BYTE *)(a1 + 144) = 0;
  v31 = v11;
  *(_QWORD *)(a1 + 232) = 0;
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  if ( *(_DWORD *)(a1 + 48) == 1 )
  {
    if ( v28 )
    {
      WapSetHttpDiagnosticInfo(a1, v28);
LABEL_51:
      v7 = v13;
      goto LABEL_8;
    }
    *(_DWORD *)(a1 + 48) = 2;
    v29 = 1;
    if ( v10 || v8 )
    {
      v6 = (volatile signed __int32 *)WapRemovePendingHttpRequest(a1);
    }
    else
    {
      v6 = (volatile signed __int32 *)WapTransferHttpRequest(a1);
      if ( v6 )
      {
        v27 = v9 == 0;
        goto LABEL_8;
      }
      if ( v9 )
      {
        v28 = 995;
        goto LABEL_51;
      }
    }
  }
  else
  {
    WapHttpCleanupQueuedRequests(a1, v33);
    v26 = *(_DWORD *)(a1 + 96);
    v28 = v26;
    if ( !*(_DWORD *)(a1 + 176) )
    {
      *(_DWORD *)(a1 + 188) = (*(_BYTE *)(a1 + 106) != 0) + 1;
      *(_DWORD *)(a1 + 176) = v26;
      *(_QWORD *)(a1 + 180) = 0;
    }
  }
LABEL_8:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( (xmmword_1800AD720 & 2) != 0 )
    WPP_SF_qqll(v15, v14, v16, a1, (__int64)v6);
  if ( v7 )
  {
    WaHttpAbortConnectionCore(*(_QWORD *)(a1 + 64), 0, v28);
    goto LABEL_21;
  }
  if ( v29 )
  {
    if ( v8 )
    {
      WapFinishHttp3Connect(a1, v6);
    }
    else
    {
      if ( !v10 )
      {
        if ( v9 )
        {
          WaCompleteConnectionOnlyRequestOnConnection((LPVOID)v6);
        }
        else
        {
          WapHttpConnectionReceive(a1, 0);
          if ( (xmmword_1800AD720 & 2) != 0 )
            WPP_SF_qqD(1025, 35, (unsigned int)WPP_c124e1a04be03a7bac98a9eabaff85fd_Traceguids, a1, (__int64)v6);
          if ( !v27 )
          {
            WaReleaseHttpConnection(a1, 0);
            goto LABEL_21;
          }
          WaSendHttpRequestOnConnection(v6, a1, 0, 0);
        }
        goto LABEL_19;
      }
      WapFinishHttp2Conversion(a1, v6);
    }
    if ( !v6 )
      goto LABEL_21;
LABEL_19:
    if ( _InterlockedExchangeAdd(v6 + 1, 0xFFFFFFFF) == 1 )
      WapDestroyHttpRequest((char *)v6);
  }
LABEL_21:
  v17 = 0;
  while ( 1 )
  {
    v18 = (_QWORD *)v33[0];
    if ( (_QWORD *)v33[0] == v33 )
      break;
    v21 = *(_QWORD *)v33[0];
    if ( *(_QWORD *)(*(_QWORD *)v33[0] + 8LL) != v33[0] || (v22 = *(_QWORD **)(v33[0] + 8LL), *v22 != v33[0]) )
      __fastfail(3u);
    *v22 = v21;
    v23 = (volatile signed __int32 *)(v18 - 15);
    *(_QWORD *)(v21 + 8) = v22;
    v18[1] = v18;
    *v18 = v18;
    v24 = 0;
    if ( *(_BYTE *)(a1 + 106) )
    {
      v24 = (*(_DWORD *)(a1 + 56) & 0x1000000) == 0;
    }
    else if ( *(_BYTE *)(a1 + 100) )
    {
      v25 = v17 | (*(_BYTE *)(a1 + 101) != 0 ? -1073741824 : 0x80000000);
      v17 = v25 | 0x8000000;
      if ( !*(_BYTE *)(a1 + 102) )
        v17 = v25;
    }
    WaHandleHttpRequestErrorFromHttpConnection((LPVOID)v23, v24);
    if ( _InterlockedExchangeAdd(v23 + 1, 0xFFFFFFFF) == 1 )
      WapDestroyHttpRequest((char *)v23);
  }
  if ( lpMem && _InterlockedExchangeAdd(lpMem + 1, 0xFFFFFFFF) == 1 )
    WapUriFreeUriObject((LPVOID)lpMem);
  if ( v31 && _InterlockedExchangeAdd(v31 + 1, 0xFFFFFFFF) == 1 )
    WapUriFreeUriObject((LPVOID)v31);
  if ( v12 && _InterlockedExchangeAdd(v12 + 1, 0xFFFFFFFF) == 1 )
    WapDestroyDnsCache((LPVOID)v12);
  v19 = *(volatile signed __int32 **)(a1 + 64);
  result = (unsigned int)_InterlockedDecrement(v19 + 1);
  if ( !(_DWORD)result )
    return WaDestroyConnection((LPVOID)v19);
  return result;
}

```

## disassembly

```asm
0x1800218e0  mov     [rsp-8+arg_10], rbx
0x1800218e5  push    rbp
0x1800218e6  push    rsi
0x1800218e7  push    rdi
0x1800218e8  push    r12
0x1800218ea  push    r13
0x1800218ec  push    r14
0x1800218ee  push    r15
0x1800218f0  lea     rbp, [rsp-27h]
0x1800218f5  sub     rsp, 90h
0x1800218fc  mov     rax, cs:__security_cookie
0x180021903  xor     rax, rsp
0x180021906  mov     [rbp+57h+var_40], rax
0x18002190a  mov     rbx, rcx
0x18002190d  mov     [rbp+57h+var_7C], edx
0x180021910  lea     rcx, [rbp+57h+var_58]
0x180021914  mov     eax, edx
0x180021916  xor     edx, edx
0x180021918  mov     [rbp+57h+var_50], rcx
0x18002191c  mov     [rbp+57h+var_60], edx
0x18002191f  lea     rcx, [rbp+57h+var_58]
0x180021923  mov     [rbp+57h+var_58], rcx
0x180021927  mov     r13, r8
0x18002192a  mov     rcx, [rbx+40h]
0x18002192e  mov     edi, edx
0x180021930  mov     [rbp+57h+var_48], rdx
0x180021934  mov     r14b, dl
0x180021937  mov     [rbp+57h+var_78], dl
0x18002193a  mov     r12b, dl
0x18002193d  mov     [rbp+57h+var_80], dl
0x180021940  movzx   r15d, byte ptr [rcx+90h]
0x180021948  movzx   esi, dl
0x18002194b  test    eax, eax
0x18002194d  jz      loc_180021BD9
0x180021953  lea     rcx, [rbx+8]; lpCriticalSection
0x180021957  call    cs:__imp_EnterCriticalSection
0x18002195e  nop     dword ptr [rax+rax+00h]
0x180021963  mov     rax, [rbx+0E8h]
0x18002196a  xor     r10d, r10d
0x18002196d  mov     [rbp+57h+lpMem], rax
0x180021971  mov     rax, [rbx+0F0h]
0x180021978  mov     [rbx+38h], r13d
0x18002197c  mov     r13, [rbx+0F8h]
0x180021983  lea     r11d, [r10+1]
0x180021987  mov     [rbx+90h], r10b
0x18002198e  mov     [rbp+57h+var_68], rax
0x180021992  mov     [rbx+0E8h], r10
0x180021999  mov     [rbx+0F0h], r10
0x1800219a0  mov     [rbx+0F8h], r10
0x1800219a7  cmp     [rbx+30h], r11d
0x1800219ab  jnz     loc_180021C27
0x1800219b1  mov     eax, [rbp+57h+var_7C]
0x1800219b4  test    eax, eax
0x1800219b6  jnz     loc_180021C9A
0x1800219bc  mov     dword ptr [rbx+30h], 2
0x1800219c3  mov     [rbp+57h+var_78], r11b
0x1800219c7  test    sil, sil
0x1800219ca  jnz     loc_180021CD7
0x1800219d0  test    r12b, r12b
0x1800219d3  jnz     loc_180021CD7
0x1800219d9  mov     rcx, rbx
0x1800219dc  call    WapTransferHttpRequest
0x1800219e1  mov     rdi, rax
0x1800219e4  test    rax, rax
0x1800219e7  jz      loc_180021CC5
0x1800219ed  test    r15b, r15b
0x1800219f0  setz    [rbp+57h+var_80]
0x1800219f4  lea     rcx, [rbx+8]; lpCriticalSection
0x1800219f8  call    cs:__imp_LeaveCriticalSection
0x1800219ff  nop     dword ptr [rax+rax+00h]
0x180021a04  test    byte ptr cs:xmmword_1800AD720, 2
0x180021a0b  jnz     loc_180021D38
0x180021a11  test    r14b, r14b
0x180021a14  jnz     loc_180021C79
0x180021a1a  cmp     [rbp+57h+var_78], r14b
0x180021a1e  jz      short loc_180021A81
0x180021a20  test    r12b, r12b
0x180021a23  jnz     loc_180021D57
0x180021a29  test    sil, sil
0x180021a2c  jnz     loc_180021CAC
0x180021a32  test    r15b, r15b
0x180021a35  jnz     loc_180021D67
0x180021a3b  xor     edx, edx
0x180021a3d  mov     rcx, rbx
0x180021a40  call    WapHttpConnectionReceive
0x180021a45  test    byte ptr cs:xmmword_1800AD720, 2
0x180021a4c  jnz     loc_180021CEE
0x180021a52  mov     sil, [rbp+57h+var_80]
0x180021a56  test    sil, sil
0x180021a59  jz      loc_180021D77
0x180021a5f  xor     r9d, r9d
0x180021a62  xor     r8d, r8d
0x180021a65  mov     rdx, rbx
0x180021a68  mov     rcx, rdi
0x180021a6b  call    WaSendHttpRequestOnConnection
0x180021a70  or      eax, 0FFFFFFFFh
0x180021a73  lock xadd [rdi+4], eax
0x180021a78  cmp     eax, 1
0x180021a7b  jz      loc_180021C6C
0x180021a81  mov     r14d, [rbp+57h+var_7C]
0x180021a85  xor     r15d, r15d
0x180021a88  mov     edi, r15d
0x180021a8b  or      r12d, 0FFFFFFFFh
0x180021a8f  mov     rax, [rbp+57h+var_58]
0x180021a93  lea     rcx, [rbp+57h+var_58]
0x180021a97  cmp     rax, rcx
0x180021a9a  jnz     loc_180021B2E
0x180021aa0  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180021aa4  test    rcx, rcx
0x180021aa7  jz      short loc_180021ABB
0x180021aa9  mov     eax, r12d
0x180021aac  lock xadd [rcx+4], eax
0x180021ab1  add     eax, r12d
0x180021ab4  jnz     short loc_180021ABB
0x180021ab6  call    WapUriFreeUriObject
0x180021abb  mov     rcx, [rbp+57h+var_68]; lpMem
0x180021abf  test    rcx, rcx
0x180021ac2  jz      short loc_180021AD6
0x180021ac4  mov     eax, r12d
0x180021ac7  lock xadd [rcx+4], eax
0x180021acc  add     eax, r12d
0x180021acf  jnz     short loc_180021AD6
0x180021ad1  call    WapUriFreeUriObject
0x180021ad6  test    r13, r13
0x180021ad9  jz      short loc_180021AF1
0x180021adb  mov     eax, r12d
0x180021ade  lock xadd [r13+4], eax
0x180021ae4  add     eax, r12d
0x180021ae7  jnz     short loc_180021AF1
0x180021ae9  mov     rcx, r13; lpMem
0x180021aec  call    WapDestroyDnsCache
0x180021af1  mov     rcx, [rbx+40h]; lpMem
0x180021af5  mov     eax, r12d
0x180021af8  lock xadd [rcx+4], eax
0x180021afd  add     eax, r12d
0x180021b00  jz      loc_180021C90
0x180021b06  mov     rcx, [rbp+57h+var_40]
0x180021b0a  xor     rcx, rsp; StackCookie
0x180021b0d  call    __security_check_cookie
0x180021b12  mov     rbx, [rsp+0C0h+arg_10]
0x180021b1a  add     rsp, 90h
0x180021b21  pop     r15
0x180021b23  pop     r14
0x180021b25  pop     r13
0x180021b27  pop     r12
0x180021b29  pop     rdi
0x180021b2a  pop     rsi
0x180021b2b  pop     rbp
0x180021b2c  retn
0x180021b2e  mov     rcx, [rax]
0x180021b31  cmp     [rcx+8], rax
0x180021b35  jnz     loc_180021CE7
0x180021b3b  mov     rdx, [rax+8]
0x180021b3f  cmp     [rdx], rax
0x180021b42  jnz     loc_180021CE7
0x180021b48  mov     [rdx], rcx
0x180021b4b  lea     rsi, [rax-78h]
0x180021b4f  mov     [rcx+8], rdx
0x180021b53  mov     r9b, r15b
0x180021b56  mov     [rax+8], rax
0x180021b5a  mov     [rax], rax
0x180021b5d  movzx   edx, r15b
0x180021b61  cmp     [rbx+6Ah], r15b
0x180021b65  jnz     loc_180021D19
0x180021b6b  mov     r8d, [rbx+38h]
0x180021b6f  mov     r10d, 1
0x180021b75  shr     r8d, 1Fh
0x180021b79  xor     r8b, r10b
0x180021b7c  cmp     [rbx+64h], r15b
0x180021b80  jz      short loc_180021BAC
0x180021b82  mov     al, [rbx+65h]
0x180021b85  neg     al
0x180021b87  sbb     ecx, ecx
0x180021b89  and     ecx, 40000000h
0x180021b8f  add     ecx, 80000000h
0x180021b95  or      ecx, edi
0x180021b97  mov     edi, ecx
0x180021b99  bts     edi, 1Bh
0x180021b9d  cmp     [rbx+66h], r15b
0x180021ba1  cmovz   edi, ecx
0x180021ba4  cmp     edi, [rbx+38h]
0x180021ba7  jnz     short loc_180021BAC
0x180021ba9  mov     r9b, r10b
0x180021bac  mov     [rsp+0C0h+var_A0], dl; char
0x180021bb0  mov     rcx, rsi; lpMem
0x180021bb3  mov     edx, r14d
0x180021bb6  call    WaHandleHttpRequestErrorFromHttpConnection
0x180021bbb  mov     eax, r12d
0x180021bbe  lock xadd [rsi+4], eax
0x180021bc3  add     eax, r12d
0x180021bc6  jnz     loc_180021A8F
0x180021bcc  mov     rcx, rsi; lpMem
0x180021bcf  call    WapDestroyHttpRequest
0x180021bd4  jmp     loc_180021A8F
0x180021bd9  cmp     [rbx+6Ah], dl
0x180021bdc  jnz     loc_180021D30
0x180021be2  cmp     [rbx+6Eh], dl
0x180021be5  jz      loc_180021953
0x180021beb  mov     rax, [rbx+48h]
0x180021bef  lea     rdx, [rbp+57h+var_48]
0x180021bf3  mov     r9d, 4
0x180021bf9  mov     qword ptr [rsp+0C0h+var_A0], rdx
0x180021bfe  lea     r8, [rbp+57h+var_60]
0x180021c02  mov     rax, [rax+48h]
0x180021c06  lea     edx, [r9+0Fh]
0x180021c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c0f  test    eax, eax
0x180021c11  jnz     loc_180021953
0x180021c17  mov     eax, 1
0x180021c1c  test    byte ptr [rbp+57h+var_60], al
0x180021c1f  cmovnz  esi, eax
0x180021c22  jmp     loc_180021953
0x180021c27  lea     rdx, [rbp+57h+var_58]
0x180021c2b  mov     rcx, rbx
0x180021c2e  call    WapHttpCleanupQueuedRequests
0x180021c33  mov     edx, [rbx+60h]
0x180021c36  xor     r8d, r8d
0x180021c39  mov     [rbp+57h+var_7C], edx
0x180021c3c  cmp     [rbx+0B0h], r8d
0x180021c43  jnz     loc_1800219F4
0x180021c49  mov     al, [rbx+6Ah]
0x180021c4c  neg     al
0x180021c4e  sbb     ecx, ecx
0x180021c50  neg     ecx
0x180021c52  inc     ecx
0x180021c54  mov     [rbx+0BCh], ecx
0x180021c5a  mov     [rbx+0B0h], edx
0x180021c60  mov     [rbx+0B4h], r8
0x180021c67  jmp     loc_1800219F4
0x180021c6c  mov     rcx, rdi; lpMem
0x180021c6f  call    WapDestroyHttpRequest
0x180021c74  jmp     loc_180021A81
0x180021c79  mov     r14d, [rbp+57h+var_7C]
0x180021c7d  xor     edx, edx
0x180021c7f  mov     rcx, [rbx+40h]
0x180021c83  mov     r8d, r14d
0x180021c86  call    WaHttpAbortConnectionCore
0x180021c8b  jmp     loc_180021A85
0x180021c90  call    WaDestroyConnection
0x180021c95  jmp     loc_180021B06
0x180021c9a  mov     edx, eax
0x180021c9c  mov     rcx, rbx
0x180021c9f  call    WapSetHttpDiagnosticInfo
0x180021ca4  mov     r14b, r11b
0x180021ca7  jmp     loc_1800219F4
0x180021cac  mov     rdx, rdi
0x180021caf  mov     rcx, rbx
0x180021cb2  call    WapFinishHttp2Conversion
0x180021cb7  test    rdi, rdi
0x180021cba  jnz     loc_180021A70
0x180021cc0  jmp     loc_180021A81
0x180021cc5  test    r15b, r15b
0x180021cc8  jz      loc_1800219F4
0x180021cce  mov     [rbp+57h+var_7C], 3E3h
0x180021cd5  jmp     short loc_180021CA4
0x180021cd7  mov     rcx, rbx
0x180021cda  call    WapRemovePendingHttpRequest
0x180021cdf  mov     rdi, rax
0x180021ce2  jmp     loc_1800219F4
0x180021ce7  mov     ecx, 3
0x180021cec  int     29h; Win8: RtlFailFast(ecx)
0x180021cee  movzx   esi, [rbp+57h+var_80]
0x180021cf2  lea     r8, WPP_c124e1a04be03a7bac98a9eabaff85fd_Traceguids
0x180021cf9  mov     [rsp+0C0h+var_98], esi
0x180021cfd  mov     edx, 23h ; '#'
0x180021d02  mov     ecx, 401h
0x180021d07  mov     qword ptr [rsp+0C0h+var_A0], rdi
0x180021d0c  mov     r9, rbx
0x180021d0f  call    WPP_SF_qqD
0x180021d14  jmp     loc_180021A56
0x180021d19  test    dword ptr [rbx+38h], 1000000h
0x180021d20  mov     eax, 1
0x180021d25  mov     r8b, r15b
0x180021d28  cmovz   edx, eax
0x180021d2b  jmp     loc_180021BAC
0x180021d30  mov     r12b, 1
0x180021d33  jmp     loc_180021953
0x180021d38  movzx   eax, r14b
0x180021d3c  mov     r9, rbx
0x180021d3f  mov     [rsp+0C0h+var_90], eax
0x180021d43  mov     [rsp+0C0h+var_98], r15d
0x180021d48  mov     qword ptr [rsp+0C0h+var_A0], rdi
0x180021d4d  call    WPP_SF_qqll
0x180021d52  jmp     loc_180021A11
0x180021d57  mov     rdx, rdi
0x180021d5a  mov     rcx, rbx
0x180021d5d  call    WapFinishHttp3Connect
0x180021d62  jmp     loc_180021CB7
0x180021d67  mov     rdx, rbx
0x180021d6a  mov     rcx, rdi; lpMem
0x180021d6d  call    WaCompleteConnectionOnlyRequestOnConnection
0x180021d72  jmp     loc_180021A70
0x180021d77  xor     edx, edx
0x180021d79  mov     rcx, rbx
0x180021d7c  call    WaReleaseHttpConnection
0x180021d81  jmp     loc_180021A81
```
