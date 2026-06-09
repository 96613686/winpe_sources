# SkeTerminateEnclaveThread

- ea: `0x140098898`
- end: `0x140098a59`
- name: `SkeTerminateEnclaveThread`
- size: `449`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1400b0f54`

## callees

- `0x1400010f0`
- `0x140002410`
- `0x140002e40`
- `0x14001bcfc`
- `0x1400202b0`
- `0x140034154`
- `0x14003acd8`
- `0x140098898`
- `0x14009b778`
- `0x1400b5a84`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkeTerminateEnclaveThread(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // r14
  char v4; // r15
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  _QWORD *v7; // rax
  __int64 v8; // rdi
  _QWORD *v9; // rcx
  __int128 v10; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v11; // [rsp+30h] [rbp-D0h]
  signed __int32 v12[64]; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(v12, 0, sizeof(v12));
  v10 = 0;
  v11 = 0;
  result = SkAcquireRundownProtection(a1 + 216);
  if ( !(_BYTE)result )
    goto LABEL_14;
  _InterlockedOr((volatile signed __int32 *)(a1 + 172), 2u);
  v3 = *(_QWORD *)(a1 + 72);
  v4 = SkAcquireSpinLockExclusive(v3 + 216);
  if ( (*(_DWORD *)(a1 + 172) & 0x400) == 0 )
  {
    v8 = *(_QWORD *)(a1 + 64);
    if ( v8 )
    {
      memset_0(v12, 0, sizeof(v12));
      _interlockedbittestandset(
        &v12[(unsigned __int64)*(unsigned __int16 *)(v8 + 180) >> 5],
        *(_WORD *)(v8 + 180) & 0x1F);
      SkeGenericIpiCall(v12, 0, 0, 0);
    }
    *(_QWORD *)&v11 = KeGetPcr()->NtTib.StackBase;
    SkAcquireSpinLockExclusiveAtDpcLevel(a1 + 16);
    v9 = *(_QWORD **)(a1 + 248);
    if ( *v9 == a1 + 240 )
    {
      *((_QWORD *)&v10 + 1) = *(_QWORD *)(a1 + 248);
      *(_QWORD *)&v10 = a1 + 240;
      *v9 = &v10;
      *(_QWORD *)(a1 + 248) = &v10;
      *(_DWORD *)(a1 + 16) = 0;
      SkTrackSpinLockRelease(&v10, &v10);
      goto LABEL_13;
    }
    goto LABEL_11;
  }
  _InterlockedAnd((volatile signed __int32 *)(a1 + 172), 0xFFFFFBFF);
  v5 = (_QWORD *)(a1 + 48);
  v6 = *(_QWORD *)(a1 + 48);
  if ( v6 )
  {
    if ( *(_QWORD **)(v6 + 8) == v5 )
    {
      v7 = *(_QWORD **)(a1 + 56);
      if ( (_QWORD *)*v7 == v5 )
      {
        *v7 = v6;
        *(_QWORD *)(v6 + 8) = v7;
        *v5 = 0;
        goto LABEL_7;
      }
    }
LABEL_11:
    __fastfail(3u);
  }
LABEL_7:
  *(_QWORD *)&v11 = a1;
LABEL_13:
  LOBYTE(v6) = v4;
  SkReleaseSpinLockExclusive(v3 + 216, v6);
  result = SkReleaseRundownProtection(a1 + 216, 0);
LABEL_14:
  if ( (_QWORD)v10 )
  {
    while ( !BYTE8(v11) )
      result = SkeWaitForAlertByThreadId(0, 0);
  }
  else if ( (_QWORD)v11 )
  {
    return SkpsDeleteEnclaveThread(a1);
  }
  return result;
}

```

## disassembly

```asm
0x140098898  push    rbp
0x14009889a  push    rbx
0x14009889b  push    rsi
0x14009889c  push    rdi
0x14009889d  push    r14
0x14009889f  push    r15
0x1400988a1  lea     rbp, [rsp-58h]
0x1400988a6  sub     rsp, 158h
0x1400988ad  mov     rax, cs:__security_cookie
0x1400988b4  xor     rax, rsp
0x1400988b7  mov     [rbp+80h+var_40], rax
0x1400988bb  mov     rbx, rcx
0x1400988be  xor     edx, edx; Val
0x1400988c0  lea     rcx, [rsp+180h+var_140]; void *
0x1400988c5  mov     r8d, 100h; Size
0x1400988cb  call    memset_0
0x1400988d0  xorps   xmm0, xmm0
0x1400988d3  lea     rsi, [rbx+0D8h]
0x1400988da  mov     rcx, rsi
0x1400988dd  movups  [rsp+180h+var_160], xmm0
0x1400988e2  movups  [rsp+180h+var_150], xmm0
0x1400988e7  call    SkAcquireRundownProtection
0x1400988ec  test    al, al
0x1400988ee  jz      loc_140098A12
0x1400988f4  lock or dword ptr [rbx+0ACh], 2
0x1400988fc  mov     r14, [rbx+48h]
0x140098900  lea     rcx, [r14+0D8h]
0x140098907  call    SkAcquireSpinLockExclusive
0x14009890c  mov     ecx, [rbx+0ACh]
0x140098912  mov     r15b, al
0x140098915  bt      ecx, 0Ah
0x140098919  jnb     short loc_140098961
0x14009891b  lock and dword ptr [rbx+0ACh], 0FFFFFBFFh
0x140098926  lea     rcx, [rbx+30h]
0x14009892a  mov     rdx, [rcx]
0x14009892d  test    rdx, rdx
0x140098930  jz      short loc_140098957
0x140098932  cmp     [rdx+8], rcx
0x140098936  jnz     loc_1400989CB
0x14009893c  mov     rax, [rcx+8]
0x140098940  cmp     [rax], rcx
0x140098943  jnz     loc_1400989CB
0x140098949  mov     [rax], rdx
0x14009894c  mov     [rdx+8], rax
0x140098950  mov     qword ptr [rcx], 0
0x140098957  mov     qword ptr [rsp+180h+var_150], rbx
0x14009895c  jmp     loc_1400989F9
0x140098961  mov     rdi, [rbx+40h]
0x140098965  test    rdi, rdi
0x140098968  jz      short loc_1400989A4
0x14009896a  xor     edx, edx; Val
0x14009896c  lea     rcx, [rsp+180h+var_140]; void *
0x140098971  mov     r8d, 100h; Size
0x140098977  call    memset_0
0x14009897c  movzx   ecx, word ptr [rdi+0B4h]
0x140098983  xor     r9d, r9d
0x140098986  mov     eax, ecx
0x140098988  xor     r8d, r8d
0x14009898b  shr     rcx, 5
0x14009898f  and     eax, 1Fh
0x140098992  xor     edx, edx
0x140098994  lock bts [rsp+rcx*4+180h+var_140], eax
0x14009899a  lea     rcx, [rsp+180h+var_140]
0x14009899f  call    SkeGenericIpiCall
0x1400989a4  mov     rax, gs:8
0x1400989ad  lea     rcx, [rbx+10h]
0x1400989b1  mov     qword ptr [rsp+180h+var_150], rax
0x1400989b6  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x1400989bb  lea     rax, [rbx+0F0h]
0x1400989c2  mov     rcx, [rax+8]
0x1400989c6  cmp     [rcx], rax
0x1400989c9  jz      short loc_1400989D2
0x1400989cb  mov     ecx, 3
0x1400989d0  int     29h; Win8: RtlFailFast(ecx)
0x1400989d2  mov     qword ptr [rsp+180h+var_160+8], rcx
0x1400989d7  lea     rdx, [rsp+180h+var_160]
0x1400989dc  mov     qword ptr [rsp+180h+var_160], rax
0x1400989e1  mov     [rcx], rdx
0x1400989e4  lea     rcx, [rsp+180h+var_160]
0x1400989e9  mov     [rax+8], rcx
0x1400989ed  mov     dword ptr [rbx+10h], 0
0x1400989f4  call    SkTrackSpinLockRelease
0x1400989f9  mov     dl, r15b
0x1400989fc  lea     rcx, [r14+0D8h]
0x140098a03  call    SkReleaseSpinLockExclusive
0x140098a08  xor     edx, edx
0x140098a0a  mov     rcx, rsi
0x140098a0d  call    SkReleaseRundownProtection
0x140098a12  cmp     qword ptr [rsp+180h+var_160], 0
0x140098a18  jnz     short loc_140098A50
0x140098a1a  cmp     qword ptr [rsp+180h+var_150], 0
0x140098a20  jz      short loc_140098A2A
0x140098a22  mov     rcx, rbx
0x140098a25  call    SkpsDeleteEnclaveThread
0x140098a2a  mov     rcx, [rbp+80h+var_40]
0x140098a2e  xor     rcx, rsp; StackCookie
0x140098a31  call    __security_check_cookie
0x140098a36  add     rsp, 158h
0x140098a3d  pop     r15
0x140098a3f  pop     r14
0x140098a41  pop     rdi
0x140098a42  pop     rsi
0x140098a43  pop     rbx
0x140098a44  pop     rbp
0x140098a45  retn
0x140098a47  xor     edx, edx
0x140098a49  xor     ecx, ecx
0x140098a4b  call    SkeWaitForAlertByThreadId
0x140098a50  cmp     byte ptr [rsp+180h+var_150+8], 0
0x140098a55  jz      short loc_140098A47
0x140098a57  jmp     short loc_140098A2A
```
