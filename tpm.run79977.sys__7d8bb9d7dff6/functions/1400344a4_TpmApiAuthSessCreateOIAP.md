# TpmApiAuthSessCreateOIAP

- ea: `0x1400344a4`
- end: `0x14003465e`
- name: `TpmApiAuthSessCreateOIAP`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140033400`

## callees

- `0x140032cc8`
- `0x1400344a4`
- `0x140034664`
- `0x1400391a0`
- `0x14003926c`
- `0x1400392c8`
- `0x1400392f0`
- `0x1400393e0`
- `0x14003950c`
- `0x1400395ac`
- `0x140039740`
- `0x140039b40`

## pseudocode

```c
__int64 __fastcall TpmApiAuthSessCreateOIAP(__int64 a1, int *a2, __int128 *a3, _DWORD *a4)
{
  int v4; // r15d
  __int64 v5; // r14
  __int128 v10; // xmm6
  int Nonce; // ecx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int128 v15; // xmm0
  int v16; // eax
  __int128 v17; // xmm0
  int v18; // eax
  __int128 *v19; // rax
  unsigned int v21; // [rsp+30h] [rbp-50h] BYREF
  int v22; // [rsp+34h] [rbp-4Ch] BYREF
  __int128 v23; // [rsp+38h] [rbp-48h] BYREF
  int v24; // [rsp+48h] [rbp-38h]
  __int128 v25; // [rsp+50h] [rbp-30h] BYREF
  int v26; // [rsp+60h] [rbp-20h]

  v22 = 0;
  v4 = 0;
  v26 = 0;
  v24 = 0;
  v21 = 0;
  v5 = 20;
  v10 = 0;
  v25 = 0;
  v23 = 0;
  if ( a2 )
  {
    if ( a4 )
    {
      memset(a4, 0, 0x48u);
      if ( a3 )
      {
        v10 = *a3;
        v4 = *((_DWORD *)a3 + 4);
      }
      Nonce = TpmApiAuthSessGetNonce(v12, &v25);
      if ( Nonce >= 0 )
      {
        Nonce = CmdBufStartCommand(a2, 193, 10);
        if ( Nonce >= 0 )
        {
          Nonce = CmdBufFinishCommand(a2);
          if ( Nonce >= 0 )
          {
            v13 = *((_QWORD *)a2 + 1);
            v14 = (unsigned int)a2[5];
            v21 = *a2;
            Nonce = TpmApiCallbackTpmCall(a1, v14, v13, &v21, v13);
            if ( Nonce >= 0 )
            {
              Nonce = CmdBufStartResult(a2, v21);
              if ( Nonce >= 0 )
              {
                Nonce = CmdBufCheckResponse(a2);
                if ( Nonce >= 0 )
                {
                  Nonce = CmdBufGetUint32(a2, &v22);
                  if ( Nonce >= 0 )
                  {
                    Nonce = CmdBufGetData(a2, 20, &v23);
                    if ( Nonce >= 0 )
                    {
                      Nonce = CmdBufFinishResult(a2);
                      if ( Nonce >= 0 )
                      {
                        v15 = v25;
                        *a4 = v22;
                        v16 = v26;
                        *((_OWORD *)a4 + 2) = v15;
                        a4[12] = v16;
                        v17 = v23;
                        v18 = v24;
                        *(_OWORD *)(a4 + 13) = v10;
                        *(_QWORD *)(a4 + 1) = 0;
                        *(_OWORD *)(a4 + 3) = v17;
                        a4[7] = v18;
                        a4[17] = v4;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      Nonce = -2144796413;
    }
  }
  else
  {
    Nonce = -2144796412;
  }
  v19 = &v23;
  do
  {
    *(_BYTE *)v19 = 0;
    v19 = (__int128 *)((char *)v19 + 1);
    --v5;
  }
  while ( v5 );
  return (unsigned int)Nonce;
}

```

## disassembly

```asm
0x1400344a4  push    rbp
0x1400344a6  push    rbx
0x1400344a7  push    rsi
0x1400344a8  push    rdi
0x1400344a9  push    r12
0x1400344ab  push    r14
0x1400344ad  push    r15
0x1400344af  mov     rbp, rsp
0x1400344b2  sub     rsp, 80h
0x1400344b9  movaps  [rsp+80h+var_10], xmm6
0x1400344be  mov     rax, cs:__security_cookie
0x1400344c5  xor     rax, rsp
0x1400344c8  mov     [rbp+var_18], rax
0x1400344cc  xor     eax, eax
0x1400344ce  mov     [rbp+var_4C], 0
0x1400344d5  xor     r15d, r15d
0x1400344d8  mov     [rbp+var_20], eax
0x1400344db  mov     [rbp+var_38], eax
0x1400344de  xorps   xmm0, xmm0
0x1400344e1  mov     [rbp+var_50], eax
0x1400344e4  xorps   xmm1, xmm1
0x1400344e7  lea     r14d, [rax+14h]
0x1400344eb  mov     rdi, r9
0x1400344ee  mov     rsi, r8
0x1400344f1  mov     rbx, rdx
0x1400344f4  mov     r12, rcx
0x1400344f7  xorps   xmm6, xmm6
0x1400344fa  movups  [rbp+var_30], xmm0
0x1400344fe  movups  [rbp+var_48], xmm1
0x140034502  test    rdx, rdx
0x140034505  jnz     short loc_140034511
0x140034507  mov     ecx, 80290104h
0x14003450c  jmp     loc_140034628
0x140034511  test    rdi, rdi
0x140034514  jnz     short loc_140034520
0x140034516  mov     ecx, 80290103h
0x14003451b  jmp     loc_140034628
0x140034520  xor     edx, edx; Val
0x140034522  mov     rcx, rdi; void *
0x140034525  lea     r8d, [rdx+48h]; Size
0x140034529  call    memset
0x14003452e  test    rsi, rsi
0x140034531  jz      short loc_14003453A
0x140034533  movups  xmm6, xmmword ptr [rsi]
0x140034536  mov     r15d, [rsi+10h]
0x14003453a  lea     rdx, [rbp+var_30]
0x14003453e  call    TpmApiAuthSessGetNonce
0x140034543  mov     ecx, eax
0x140034545  test    eax, eax
0x140034547  js      loc_140034628
0x14003454d  mov     edx, 0C1h
0x140034552  mov     r8d, 0Ah
0x140034558  mov     rcx, rbx
0x14003455b  call    CmdBufStartCommand
0x140034560  mov     ecx, eax
0x140034562  test    eax, eax
0x140034564  js      loc_140034628
0x14003456a  mov     rcx, rbx
0x14003456d  call    CmdBufFinishCommand
0x140034572  mov     ecx, eax
0x140034574  test    eax, eax
0x140034576  js      loc_140034628
0x14003457c  mov     r8, [rbx+8]
0x140034580  lea     r9, [rbp+var_50]
0x140034584  mov     eax, [rbx]
0x140034586  mov     rcx, r12
0x140034589  mov     edx, [rbx+14h]
0x14003458c  mov     [rsp+80h+var_60], r8
0x140034591  mov     [rbp+var_50], eax
0x140034594  call    TpmApiCallbackTpmCall
0x140034599  mov     ecx, eax
0x14003459b  test    eax, eax
0x14003459d  js      loc_140034628
0x1400345a3  mov     edx, [rbp+var_50]
0x1400345a6  mov     rcx, rbx
0x1400345a9  call    CmdBufStartResult
0x1400345ae  mov     ecx, eax
0x1400345b0  test    eax, eax
0x1400345b2  js      short loc_140034628
0x1400345b4  mov     rcx, rbx
0x1400345b7  call    CmdBufCheckResponse
0x1400345bc  mov     ecx, eax
0x1400345be  test    eax, eax
0x1400345c0  js      short loc_140034628
0x1400345c2  lea     rdx, [rbp+var_4C]
0x1400345c6  mov     rcx, rbx
0x1400345c9  call    CmdBufGetUint32
0x1400345ce  mov     ecx, eax
0x1400345d0  test    eax, eax
0x1400345d2  js      short loc_140034628
0x1400345d4  lea     r8, [rbp+var_48]
0x1400345d8  mov     edx, r14d
0x1400345db  mov     rcx, rbx
0x1400345de  call    CmdBufGetData
0x1400345e3  mov     ecx, eax
0x1400345e5  test    eax, eax
0x1400345e7  js      short loc_140034628
0x1400345e9  mov     rcx, rbx
0x1400345ec  call    CmdBufFinishResult
0x1400345f1  mov     ecx, eax
0x1400345f3  test    eax, eax
0x1400345f5  js      short loc_140034628
0x1400345f7  movups  xmm0, [rbp+var_30]
0x1400345fb  mov     eax, [rbp+var_4C]
0x1400345fe  mov     [rdi], eax
0x140034600  mov     eax, [rbp+var_20]
0x140034603  movups  xmmword ptr [rdi+20h], xmm0
0x140034607  mov     [rdi+30h], eax
0x14003460a  movups  xmm0, [rbp+var_48]
0x14003460e  mov     eax, [rbp+var_38]
0x140034611  movups  xmmword ptr [rdi+34h], xmm6
0x140034615  mov     qword ptr [rdi+4], 0
0x14003461d  movups  xmmword ptr [rdi+0Ch], xmm0
0x140034621  mov     [rdi+1Ch], eax
0x140034624  mov     [rdi+44h], r15d
0x140034628  lea     rax, [rbp+var_48]
0x14003462c  mov     byte ptr [rax], 0
0x14003462f  inc     rax
0x140034632  sub     r14, 1
0x140034636  jnz     short loc_14003462C
0x140034638  mov     eax, ecx
0x14003463a  mov     rcx, [rbp+var_18]
0x14003463e  xor     rcx, rsp; StackCookie
0x140034641  call    __security_check_cookie
0x140034646  movaps  xmm6, [rsp+80h+var_10]
0x14003464b  add     rsp, 80h
0x140034652  pop     r15
0x140034654  pop     r14
0x140034656  pop     r12
0x140034658  pop     rdi
0x140034659  pop     rsi
0x14003465a  pop     rbx
0x14003465b  pop     rbp
0x14003465c  retn
```
