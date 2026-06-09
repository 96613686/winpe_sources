# UdfRmwFlushCache

- ea: `0x14000ba88`
- end: `0x14000bef7`
- name: `UdfRmwFlushCache`
- size: `1135`
- prototype: `__int64 __fastcall(int)`
- caller_count: `4`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000a3f0`
- `0x140035794`
- `0x140052864`
- `0x140059540`

## callees

- `0x14000ba88`
- `0x14000ca10`
- `0x14000cad4`
- `0x140017498`
- `0x14001b674`
- `0x14001b770`
- `0x14001b938`
- `0x14001c080`
- `0x14003cbec`
- `0x140058114`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000bbad`
- `ntoskrnl!RtlCompareMemory` at `0x14000bbad`

## pseudocode

```c
__int64 __fastcall UdfRmwFlushCache(__int64 a1, __int64 a2, int a3, char a4)
{
  unsigned int v4; // r13d
  char v5; // al
  unsigned int v8; // r14d
  char v9; // r15
  _QWORD *v10; // rcx
  char v11; // dl
  _QWORD *v12; // r12
  _QWORD *v13; // rbx
  bool v14; // zf
  int v15; // ecx
  int v16; // edx
  int v17; // eax
  __int64 v18; // rdx
  int CacheRunValid; // edi
  SIZE_T v20; // rax
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rdx
  _DWORD *v24; // rcx
  __int64 v25; // rdx
  int v26; // ecx
  __int64 v27; // rcx
  __int64 v29; // rdx
  char i; // [rsp+30h] [rbp-48h]
  char v31; // [rsp+31h] [rbp-47h]
  char v32; // [rsp+32h] [rbp-46h]
  int v33; // [rsp+34h] [rbp-44h] BYREF
  _QWORD *v34; // [rsp+38h] [rbp-40h]
  int v35; // [rsp+90h] [rbp+18h]

  v35 = a3;
  v4 = 0;
  v33 = 0;
  v5 = 1;
  v32 = 0;
  v31 = 1;
  v8 = 1;
  v9 = 0;
  while ( v8 <= 3 )
  {
    if ( v8 != 3 || !v5 )
    {
      v10 = (_QWORD *)(a2 + 40);
      v11 = 0;
      v12 = *(_QWORD **)(a2 + 40);
      for ( i = 0; ; v11 = i )
      {
LABEL_11:
        if ( v11 )
          goto LABEL_9;
        if ( v12 == v10 )
          goto LABEL_9;
        v13 = v12 - 4;
        v14 = *((_DWORD *)v12 - 8) == -1;
        v34 = v12 - 4;
        if ( v14 )
          goto LABEL_9;
        v15 = *((_DWORD *)v13 + 16);
        v16 = v15 & 2;
        if ( (v15 & 2) == 0 || !v5 )
          break;
        if ( v8 == 1 )
          ++v4;
        v12 = (_QWORD *)*v12;
        v10 = (_QWORD *)(a2 + 40);
      }
      if ( v8 == 1 )
      {
        if ( (v15 & 1) != 0 )
        {
          CacheRunValid = UdfRmwMakeCacheRunValid(a1, a3);
          if ( CacheRunValid < 0 )
          {
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                41,
                WPP_e04914546632397e8b30a0a107c62418_Traceguids);
            }
            v13 = v34;
            goto LABEL_66;
          }
          goto LABEL_38;
        }
      }
      else if ( v8 == 2 )
      {
        if ( (v15 & 1) != 0 )
        {
          v24 = *(_DWORD **)(a1 + 16);
          if ( (v24[532] & 0x40) != 0 && *((_DWORD *)v13 + 2) > v24[171] )
          {
            memset(*(void **)(a2 + 24), 0, (unsigned int)(*(_DWORD *)(a2 + 12) << v24[18]));
            while ( 1 )
            {
              LOBYTE(v16) = 1;
              if ( (int)UdfRmwIssueIoRequest(
                          a1,
                          v16,
                          *(_DWORD *)(*(_QWORD *)(a1 + 16) + 684LL),
                          *(_DWORD *)(a2 + 12),
                          *(PVOID *)(a2 + 24)) < 0 )
                break;
              *(_DWORD *)(*(_QWORD *)(a1 + 16) + 684LL) += *(_DWORD *)(a2 + 12);
              if ( *((_DWORD *)v13 + 2) <= *(_DWORD *)(*(_QWORD *)(a1 + 16) + 684LL) )
                goto LABEL_51;
            }
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                42,
                WPP_e04914546632397e8b30a0a107c62418_Traceguids);
            }
          }
LABEL_51:
          LOBYTE(v16) = 1;
          CacheRunValid = UdfRmwIssueIoRequest(a1, v16, *((_DWORD *)v13 + 2), *(_DWORD *)(a2 + 12), (PVOID)v13[2]);
          if ( CacheRunValid >= 0 )
          {
            v25 = *(_QWORD *)(a1 + 16);
            if ( (*(_DWORD *)(v25 + 2128) & 0x40) != 0 )
            {
              v26 = *(_DWORD *)(v25 + 684);
              if ( *((_DWORD *)v13 + 2) == v26 )
                *(_DWORD *)(v25 + 684) = *(_DWORD *)(a2 + 12) + v26;
            }
            *((_DWORD *)v13 + 16) &= ~1u;
          }
          else
          {
            v22 = *(_QWORD *)&WPP_GLOBAL_Control;
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
            {
              v23 = 43;
LABEL_55:
              WPP_SF_d(*(_QWORD *)(v22 + 24), v23, WPP_e04914546632397e8b30a0a107c62418_Traceguids);
            }
LABEL_66:
            if ( a4 )
              return (unsigned int)CacheRunValid;
            LOBYTE(v18) = 1;
            UdfMarkVolumeCorrupt(a1, v18);
            v9 = 1;
            UdfRmwMakeCacheRunInvalid(v27, a2, v13);
          }
          goto LABEL_38;
        }
      }
      else if ( v8 == 3 && (v15 & 2) != 0 )
      {
        v17 = UdfRmwIssueIoRequest(a1, 0, *((_DWORD *)v13 + 2), *(_DWORD *)(a2 + 12), *(PVOID *)(a2 + 24));
        CacheRunValid = v17;
        if ( v17 < 0 )
        {
          if ( v17 != -1073741670 )
            goto LABEL_30;
          goto LABEL_66;
        }
        v20 = RtlCompareMemory(
                (const void *)v13[2],
                *(const void **)(a2 + 24),
                (unsigned int)(*(_DWORD *)(a2 + 12) << *(_DWORD *)(*(_QWORD *)(a1 + 16) + 72LL)));
        v18 = (unsigned int)(*(_DWORD *)(a2 + 12) << *(_DWORD *)(*(_QWORD *)(a1 + 16) + 72LL));
        if ( v20 != v18 )
        {
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
          {
            WPP_SF_(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
              44,
              WPP_e04914546632397e8b30a0a107c62418_Traceguids);
          }
          CacheRunValid = -1073741761;
LABEL_30:
          if ( CacheRunValid < 0 )
          {
            if ( (v13[8] & 4) != 0 )
            {
              CacheRunValid = UdfSparePacket(a1, *(_DWORD *)v13, &v33);
              if ( CacheRunValid >= 0 )
              {
                v21 = v33;
                v8 = 1;
                *((_DWORD *)v13 + 2) = v33;
                v11 = 1;
                *((_DWORD *)v13 + 1) = v21;
                *((_DWORD *)v13 + 16) |= 1u;
                i = 1;
                v32 = 1;
                goto LABEL_39;
              }
            }
            v22 = *(_QWORD *)&WPP_GLOBAL_Control;
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
            {
              v23 = 45;
              goto LABEL_55;
            }
            goto LABEL_66;
          }
        }
        *((_DWORD *)v13 + 16) &= 0xFFFFFFF9;
LABEL_38:
        v11 = i;
LABEL_39:
        a3 = v35;
LABEL_40:
        v12 = (_QWORD *)*v12;
        v10 = (_QWORD *)(a2 + 40);
        v5 = v31;
        goto LABEL_11;
      }
      v11 = i;
      goto LABEL_40;
    }
    if ( ((a3 & 8) == 0 || !v4) && v4 <= *(_DWORD *)(a2 + 8) >> 1 )
      break;
    v5 = 0;
    v31 = 0;
    v8 = 0;
LABEL_9:
    ++v8;
  }
  if ( v32 && (int)UdfWriteSparingTable(a1) < 0 )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 46, WPP_e04914546632397e8b30a0a107c62418_Traceguids);
    }
    LOBYTE(v29) = 1;
    UdfMarkVolumeCorrupt(a1, v29);
    v9 = 1;
  }
  return v9 != 0 ? 0xC0000032 : 0;
}

```

## disassembly

```asm
0x14000ba88  mov     rax, rsp
0x14000ba8b  mov     [rax+8], rbx
0x14000ba8f  mov     [rax+20h], r9b
0x14000ba93  mov     [rax+18h], r8d
0x14000ba97  push    rbp
0x14000ba98  push    rsi
0x14000ba99  push    rdi
0x14000ba9a  push    r12
0x14000ba9c  push    r13
0x14000ba9e  push    r14
0x14000baa0  push    r15
0x14000baa2  sub     rsp, 40h
0x14000baa6  xor     r13d, r13d
0x14000baa9  mov     dword ptr [rax-44h], 0
0x14000bab0  mov     al, 1
0x14000bab2  mov     [rsp+78h+var_46], r13b
0x14000bab7  mov     rbp, rdx
0x14000baba  mov     [rsp+78h+var_47], al
0x14000babe  mov     rsi, rcx
0x14000bac1  lea     rdi, WPP_GLOBAL_Control
0x14000bac8  lea     r14d, [r13+1]
0x14000bacc  xor     r15b, r15b
0x14000bacf  cmp     r14d, 3
0x14000bad3  ja      loc_14000BE87
0x14000bad9  jnz     short loc_14000BB06
0x14000badb  test    al, al
0x14000badd  jz      short loc_14000BB06
0x14000badf  test    r8b, 8
0x14000bae3  jz      short loc_14000BAEA
0x14000bae5  test    r13d, r13d
0x14000bae8  jnz     short loc_14000BAF8
0x14000baea  mov     eax, [rbp+8]
0x14000baed  shr     eax, 1
0x14000baef  cmp     r13d, eax
0x14000baf2  jbe     loc_14000BE87
0x14000baf8  xor     al, al
0x14000bafa  mov     [rsp+78h+var_47], al
0x14000bafe  xor     r14d, r14d
0x14000bb01  inc     r14d
0x14000bb04  jmp     short loc_14000BACF
0x14000bb06  lea     rcx, [rbp+28h]
0x14000bb0a  xor     dl, dl
0x14000bb0c  mov     r12, [rcx]
0x14000bb0f  mov     [rsp+78h+var_48], dl
0x14000bb13  test    dl, dl
0x14000bb15  jnz     short loc_14000BB01
0x14000bb17  cmp     r12, rcx
0x14000bb1a  jz      short loc_14000BB01
0x14000bb1c  lea     rbx, [r12-20h]
0x14000bb21  cmp     dword ptr [rbx], 0FFFFFFFFh
0x14000bb24  mov     [rsp+78h+var_40], rbx
0x14000bb29  jz      short loc_14000BB01
0x14000bb2b  mov     ecx, [rbx+40h]
0x14000bb2e  mov     edx, ecx
0x14000bb30  and     edx, 2
0x14000bb33  jz      short loc_14000BB50
0x14000bb35  test    al, al
0x14000bb37  jz      short loc_14000BB50
0x14000bb39  cmp     r14d, 1
0x14000bb3d  jnz     short loc_14000BB42
0x14000bb3f  inc     r13d
0x14000bb42  mov     r12, [r12]
0x14000bb46  lea     rcx, [rbp+28h]
0x14000bb4a  mov     dl, [rsp+78h+var_48]
0x14000bb4e  jmp     short loc_14000BB13
0x14000bb50  mov     eax, r14d
0x14000bb53  sub     eax, 1
0x14000bb56  jz      loc_14000BDE8
0x14000bb5c  sub     eax, 1
0x14000bb5f  jz      loc_14000BCAB
0x14000bb65  cmp     eax, 1
0x14000bb68  jnz     loc_14000BE7A
0x14000bb6e  test    edx, edx
0x14000bb70  jz      loc_14000BE7A
0x14000bb76  mov     rax, [rbp+18h]
0x14000bb7a  xor     edx, edx; int
0x14000bb7c  mov     r9d, [rbp+0Ch]; int
0x14000bb80  mov     rcx, rsi; int
0x14000bb83  mov     r8d, [rbx+8]; int
0x14000bb87  mov     [rsp+78h+VirtualAddress], rax; VirtualAddress
0x14000bb8c  call    UdfRmwIssueIoRequest
0x14000bb91  mov     edi, eax
0x14000bb93  test    eax, eax
0x14000bb95  js      short loc_14000BC08
0x14000bb97  mov     rcx, [rsi+10h]
0x14000bb9b  mov     r8d, [rbp+0Ch]
0x14000bb9f  mov     rdx, [rbp+18h]; Source2
0x14000bba3  mov     ecx, [rcx+48h]
0x14000bba6  shl     r8d, cl; Length
0x14000bba9  mov     rcx, [rbx+10h]; Source1
0x14000bbad  call    cs:__imp_RtlCompareMemory
0x14000bbb4  nop     dword ptr [rax+rax+00h]
0x14000bbb9  mov     rcx, [rsi+10h]
0x14000bbbd  mov     edx, [rbp+0Ch]
0x14000bbc0  mov     ecx, [rcx+48h]
0x14000bbc3  shl     edx, cl
0x14000bbc5  mov     ecx, edx
0x14000bbc7  cmp     rax, rcx
0x14000bbca  jz      loc_14000BC83
0x14000bbd0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bbd7  lea     rax, WPP_GLOBAL_Control
0x14000bbde  cmp     rcx, rax
0x14000bbe1  jz      short loc_14000BC01
0x14000bbe3  test    dword ptr [rcx+2Ch], 20000000h
0x14000bbea  jz      short loc_14000BC01
0x14000bbec  mov     rcx, [rcx+18h]
0x14000bbf0  lea     r8, WPP_e04914546632397e8b30a0a107c62418_Traceguids
0x14000bbf7  mov     edx, 2Ch ; ','
0x14000bbfc  call    WPP_SF_
0x14000bc01  mov     edi, 0C000003Fh
0x14000bc06  jmp     short loc_14000BC13
0x14000bc08  cmp     eax, 0C000009Ah
0x14000bc0d  jz      loc_14000BE53
0x14000bc13  test    edi, edi
0x14000bc15  jns     short loc_14000BC83
0x14000bc17  mov     eax, [rbx+40h]
0x14000bc1a  test    al, 4
0x14000bc1c  jz      short loc_14000BC55
0x14000bc1e  mov     edx, [rbx]
0x14000bc20  lea     r8, [rsp+78h+var_44]
0x14000bc25  mov     rcx, rsi
0x14000bc28  call    UdfSparePacket
0x14000bc2d  mov     edi, eax
0x14000bc2f  test    eax, eax
0x14000bc31  js      short loc_14000BC55
0x14000bc33  mov     eax, [rsp+78h+var_44]
0x14000bc37  mov     r14d, 1
0x14000bc3d  mov     [rbx+8], eax
0x14000bc40  mov     dl, r14b
0x14000bc43  mov     [rbx+4], eax
0x14000bc46  or      dword ptr [rbx+40h], 1
0x14000bc4a  mov     [rsp+78h+var_48], dl
0x14000bc4e  mov     [rsp+78h+var_46], 1
0x14000bc53  jmp     short loc_14000BC8B
0x14000bc55  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc5c  lea     rax, WPP_GLOBAL_Control
0x14000bc63  cmp     rcx, rax
0x14000bc66  jz      loc_14000BE53
0x14000bc6c  test    dword ptr [rcx+2Ch], 20000000h
0x14000bc73  jz      loc_14000BE53
0x14000bc79  mov     edx, 2Dh ; '-'
0x14000bc7e  jmp     loc_14000BDA5
0x14000bc83  and     dword ptr [rbx+40h], 0FFFFFFF9h
0x14000bc87  mov     dl, [rsp+78h+var_48]
0x14000bc8b  mov     r8d, [rsp+78h+arg_10]
0x14000bc93  lea     rdi, WPP_GLOBAL_Control
0x14000bc9a  mov     r12, [r12]
0x14000bc9e  lea     rcx, [rbp+28h]
0x14000bca2  mov     al, [rsp+78h+var_47]
0x14000bca6  jmp     loc_14000BB13
0x14000bcab  test    cl, 1
0x14000bcae  jz      loc_14000BE7A
0x14000bcb4  mov     rcx, [rsi+10h]
0x14000bcb8  mov     eax, [rcx+850h]
0x14000bcbe  test    al, 40h
0x14000bcc0  jz      loc_14000BD5B
0x14000bcc6  mov     eax, [rcx+2ACh]
0x14000bccc  cmp     [rbx+8], eax
0x14000bccf  jbe     loc_14000BD5B
0x14000bcd5  mov     ecx, [rcx+48h]
0x14000bcd8  xor     edx, edx; Val
0x14000bcda  mov     r8d, [rbp+0Ch]
0x14000bcde  shl     r8d, cl; Size
0x14000bce1  mov     rcx, [rbp+18h]; void *
0x14000bce5  call    memset
0x14000bcea  mov     r8, [rsi+10h]
0x14000bcee  mov     dl, 1; int
0x14000bcf0  mov     rax, [rbp+18h]
0x14000bcf4  mov     rcx, rsi; int
0x14000bcf7  mov     r9d, [rbp+0Ch]; int
0x14000bcfb  mov     [rsp+78h+VirtualAddress], rax; VirtualAddress
0x14000bd00  mov     r8d, [r8+2ACh]; int
0x14000bd07  call    UdfRmwIssueIoRequest
0x14000bd0c  mov     r9d, eax
0x14000bd0f  test    eax, eax
0x14000bd11  js      short loc_14000BD31
0x14000bd13  mov     rcx, [rsi+10h]
0x14000bd17  mov     eax, [rbp+0Ch]
0x14000bd1a  add     [rcx+2ACh], eax
0x14000bd20  mov     rax, [rsi+10h]
0x14000bd24  mov     ecx, [rax+2ACh]
0x14000bd2a  cmp     [rbx+8], ecx
0x14000bd2d  ja      short loc_14000BCEA
0x14000bd2f  jmp     short loc_14000BD5B
0x14000bd31  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bd38  cmp     rcx, rdi
0x14000bd3b  jz      short loc_14000BD5B
0x14000bd3d  test    dword ptr [rcx+2Ch], 20000000h
0x14000bd44  jz      short loc_14000BD5B
0x14000bd46  mov     rcx, [rcx+18h]
0x14000bd4a  lea     r8, WPP_e04914546632397e8b30a0a107c62418_Traceguids
0x14000bd51  mov     edx, 2Ah ; '*'
0x14000bd56  call    WPP_SF_d
0x14000bd5b  mov     rax, [rbx+10h]
0x14000bd5f  mov     dl, 1; int
0x14000bd61  mov     r9d, [rbp+0Ch]; int
0x14000bd65  mov     rcx, rsi; int
0x14000bd68  mov     r8d, [rbx+8]; int
0x14000bd6c  mov     [rsp+78h+VirtualAddress], rax; VirtualAddress
0x14000bd71  call    UdfRmwIssueIoRequest
0x14000bd76  mov     edi, eax
0x14000bd78  test    eax, eax
0x14000bd7a  jns     short loc_14000BDBD
0x14000bd7c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bd83  lea     rax, WPP_GLOBAL_Control
0x14000bd8a  cmp     rcx, rax
0x14000bd8d  jz      loc_14000BE53
0x14000bd93  test    dword ptr [rcx+2Ch], 20000000h
0x14000bd9a  jz      loc_14000BE53
0x14000bda0  mov     edx, 2Bh ; '+'
0x14000bda5  mov     rcx, [rcx+18h]
0x14000bda9  lea     r8, WPP_e04914546632397e8b30a0a107c62418_Traceguids
0x14000bdb0  mov     r9d, edi
0x14000bdb3  call    WPP_SF_d
0x14000bdb8  jmp     loc_14000BE53
0x14000bdbd  mov     rdx, [rsi+10h]
0x14000bdc1  mov     eax, [rdx+850h]
0x14000bdc7  test    al, 40h
0x14000bdc9  jz      short loc_14000BDDF
0x14000bdcb  mov     ecx, [rdx+2ACh]
0x14000bdd1  cmp     [rbx+8], ecx
0x14000bdd4  jnz     short loc_14000BDDF
0x14000bdd6  add     ecx, [rbp+0Ch]
0x14000bdd9  mov     [rdx+2ACh], ecx
0x14000bddf  and     dword ptr [rbx+40h], 0FFFFFFFEh
0x14000bde3  jmp     loc_14000BC87
0x14000bde8  test    cl, 1
0x14000bdeb  jz      loc_14000BE7A
0x14000bdf1  mov     dword ptr [rsp+78h+VirtualAddress], r8d; int
0x14000bdf6  lea     r9, [rsp+78h+var_45]
0x14000bdfb  lea     r8, [rsp+78h+var_40]
0x14000be00  mov     [rsp+78h+var_45], 1
0x14000be05  mov     rdx, rbp
0x14000be08  mov     rcx, rsi; int
0x14000be0b  call    UdfRmwMakeCacheRunValid
0x14000be10  mov     edi, eax
0x14000be12  test    eax, eax
0x14000be14  jns     loc_14000BC87
0x14000be1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000be21  lea     rax, WPP_GLOBAL_Control
0x14000be28  cmp     rcx, rax
0x14000be2b  jz      short loc_14000BE4E
0x14000be2d  test    dword ptr [rcx+2Ch], 20000000h
0x14000be34  jz      short loc_14000BE4E
0x14000be36  mov     rcx, [rcx+18h]
0x14000be3a  lea     r8, WPP_e04914546632397e8b30a0a107c62418_Traceguids
0x14000be41  mov     edx, 29h ; ')'
0x14000be46  mov     r9d, edi
0x14000be49  call    WPP_SF_d
0x14000be4e  mov     rbx, [rsp+78h+var_40]
0x14000be53  cmp     [rsp+78h+arg_18], 0
0x14000be5b  jnz     short loc_14000BE83
0x14000be5d  mov     dl, 1
0x14000be5f  mov     rcx, rsi
0x14000be62  call    UdfMarkVolumeCorrupt
0x14000be67  mov     r8, rbx
0x14000be6a  mov     rdx, rbp
0x14000be6d  mov     r15b, 1
0x14000be70  call    UdfRmwMakeCacheRunInvalid
0x14000be75  jmp     loc_14000BC87
0x14000be7a  mov     dl, [rsp+78h+var_48]
0x14000be7e  jmp     loc_14000BC9A
0x14000be83  mov     eax, edi
0x14000be85  jmp     short loc_14000BEDE
0x14000be87  cmp     [rsp+78h+var_46], 0
0x14000be8c  jz      short loc_14000BED4
0x14000be8e  mov     rcx, rsi
0x14000be91  call    UdfWriteSparingTable
0x14000be96  test    eax, eax
0x14000be98  jns     short loc_14000BED4
0x14000be9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bea1  cmp     rcx, rdi
0x14000bea4  jz      short loc_14000BEC7
0x14000bea6  test    dword ptr [rcx+2Ch], 20000000h
0x14000bead  jz      short loc_14000BEC7
0x14000beaf  mov     rcx, [rcx+18h]
0x14000beb3  lea     r8, WPP_e04914546632397e8b30a0a107c62418_Traceguids
0x14000beba  mov     edx, 2Eh ; '.'
0x14000bebf  mov     r9d, eax
0x14000bec2  call    WPP_SF_d
0x14000bec7  mov     dl, 1
0x14000bec9  mov     rcx, rsi
0x14000becc  call    UdfMarkVolumeCorrupt
0x14000bed1  mov     r15b, 1
0x14000bed4  neg     r15b
0x14000bed7  sbb     eax, eax
0x14000bed9  and     eax, 0C0000032h
0x14000bede  mov     rbx, [rsp+78h+arg_0]
0x14000bee6  add     rsp, 40h
0x14000beea  pop     r15
0x14000beec  pop     r14
0x14000beee  pop     r13
0x14000bef0  pop     r12
0x14000bef2  pop     rdi
0x14000bef3  pop     rsi
0x14000bef4  pop     rbp
0x14000bef5  retn
```
