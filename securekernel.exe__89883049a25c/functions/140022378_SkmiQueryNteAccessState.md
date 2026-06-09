# SkmiQueryNteAccessState

- ea: `0x140022378`
- end: `0x1400224dc`
- name: `SkmiQueryNteAccessState`
- size: `356`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140014dd0`

## callees

- `0x14000e810`
- `0x14000ff70`
- `0x140013bf8`
- `0x140020360`
- `0x140020424`
- `0x140022378`
- `0x140024fac`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiQueryNteAccessState(__int64 a1, char a2)
{
  unsigned __int64 v4; // rdx
  __int64 v5; // rcx
  char v6; // si
  __int64 v7; // rdi
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // r9
  volatile signed __int64 *ValidNteAddress; // r10
  __int64 v12; // r11
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  _BYTE v16[256]; // [rsp+20h] [rbp-138h] BYREF
  unsigned int v17; // [rsp+120h] [rbp-38h]
  char v18; // [rsp+124h] [rbp-34h]
  char v19; // [rsp+125h] [rbp-33h]

  memset_0(v16, 0, 0x108u);
  v6 = SkAcquireSpinLockShared(&SkmiNteLock);
  v7 = 0;
  do
  {
    v8 = *(_QWORD *)(a1 + 8 * v7);
    if ( !v8 )
      break;
    ValidNteAddress = (volatile signed __int64 *)SkmiGetValidNteAddress(v8 & 0xFFFFFFFFFFFFF000uLL, v4, v8);
    if ( ValidNteAddress )
    {
LABEL_5:
      v13 = *ValidNteAddress;
      if ( a2 )
      {
        while ( (v13 & 0x800) == 0
             && ((v13 & 0x801) == 1 || (v13 & 0x100) != 0)
             && (v13 & 0x20) != 0
             && (SkmiFlags & 0x1000000) != 0 )
        {
          if ( (v13 & 0x400) != 0 )
          {
            _mm_pause();
            goto LABEL_5;
          }
          v14 = v13;
          v4 = v13 & 0xFFFFFFFFFFFFFFDFuLL;
          v13 = _InterlockedCompareExchange64(ValidNteAddress, v13 & 0xFFFFFFFFFFFFFFDFuLL, v13);
          if ( v13 == v14 )
          {
            v5 = 1;
            goto LABEL_16;
          }
        }
      }
      v5 = 0;
LABEL_16:
      if ( (v13 & 0x800) != 0 )
      {
        *(_QWORD *)(a1 + 8 * v7) |= 2uLL;
      }
      else if ( (v13 & 1) != 0 )
      {
        v4 = *(_QWORD *)(a1 + 8 * v7) & 0xFFFFFFFFFFFFFFFEuLL;
        *(_QWORD *)(a1 + 8 * v7) = v4 | (v13 >> 5) & 1;
      }
      else
      {
        *(_QWORD *)(a1 + 8 * v7) &= ~1uLL;
      }
      if ( (_DWORD)v5 )
        SkmiBatchFlushSingleTb(v12, v16, v9, v10);
    }
    else
    {
      *(_QWORD *)(a1 + 8 * v7) = v9 | 2;
    }
    v7 = (unsigned int)(v7 + 1);
  }
  while ( (unsigned int)v7 < 0xB );
  if ( v18 )
  {
    LOBYTE(v5) = v19;
    SkeFlushEntireTb(v5, 0);
  }
  else if ( v17 )
  {
    LOBYTE(v5) = v19;
    SkeFlushRangeListTb(v5, 0, v17, v16);
  }
  LOBYTE(v4) = v6;
  return RtlpReleasePropStoreLockShared(&SkmiNteLock, v4);
}

```

## disassembly

```asm
0x140022378  push    rbx
0x14002237a  push    rbp
0x14002237b  push    rsi
0x14002237c  push    rdi
0x14002237d  sub     rsp, 138h
0x140022384  mov     bpl, dl
0x140022387  mov     rbx, rcx
0x14002238a  xor     edx, edx; Val
0x14002238c  lea     rcx, [rsp+158h+var_138]; void *
0x140022391  mov     r8d, 108h; Size
0x140022397  call    memset_0
0x14002239c  lea     rcx, SkmiNteLock
0x1400223a3  call    SkAcquireSpinLockShared
0x1400223a8  mov     sil, al
0x1400223ab  xor     edi, edi
0x1400223ad  mov     r8, [rbx+rdi*8]
0x1400223b1  test    r8, r8
0x1400223b4  jz      loc_140022486
0x1400223ba  mov     r11, r8
0x1400223bd  and     r11, 0FFFFFFFFFFFFF000h
0x1400223c4  mov     rcx, r11
0x1400223c7  call    SkmiGetValidNteAddress
0x1400223cc  mov     r10, rax
0x1400223cf  test    rax, rax
0x1400223d2  jnz     short loc_1400223E1
0x1400223d4  or      r8, 2
0x1400223d8  mov     [rbx+rdi*8], r8
0x1400223dc  jmp     loc_14002247B
0x1400223e1  mov     rax, [r10]
0x1400223e4  test    bpl, bpl
0x1400223e7  jz      short loc_140022439
0x1400223e9  bt      rax, 0Bh
0x1400223ee  jb      short loc_140022439
0x1400223f0  mov     rcx, rax
0x1400223f3  and     ecx, 801h
0x1400223f9  cmp     rcx, 1
0x1400223fd  jz      short loc_140022406
0x1400223ff  bt      rax, 8
0x140022404  jnb     short loc_140022439
0x140022406  test    al, 20h
0x140022408  jz      short loc_140022439
0x14002240a  test    byte ptr cs:SkmiFlags+3, 1
0x140022411  jz      short loc_140022439
0x140022413  bt      rax, 0Ah
0x140022418  jb      short loc_140022435
0x14002241a  mov     rdx, rax
0x14002241d  mov     rcx, rax
0x140022420  and     rdx, 0FFFFFFFFFFFFFFDFh
0x140022424  lock cmpxchg [r10], rdx
0x140022429  cmp     rax, rcx
0x14002242c  jnz     short loc_1400223E9
0x14002242e  mov     ecx, 1
0x140022433  jmp     short loc_14002243B
0x140022435  pause
0x140022437  jmp     short loc_1400223E1
0x140022439  xor     ecx, ecx
0x14002243b  bt      rax, 0Bh
0x140022440  jnb     short loc_140022449
0x140022442  or      qword ptr [rbx+rdi*8], 2
0x140022447  jmp     short loc_14002246A
0x140022449  test    al, 1
0x14002244b  jnz     short loc_140022454
0x14002244d  and     qword ptr [rbx+rdi*8], 0FFFFFFFFFFFFFFFEh
0x140022452  jmp     short loc_14002246A
0x140022454  mov     rdx, [rbx+rdi*8]
0x140022458  shr     rax, 5
0x14002245c  and     rdx, 0FFFFFFFFFFFFFFFEh
0x140022460  and     eax, 1
0x140022463  or      rax, rdx
0x140022466  mov     [rbx+rdi*8], rax
0x14002246a  test    ecx, ecx
0x14002246c  jz      short loc_14002247B
0x14002246e  lea     rdx, [rsp+158h+var_138]
0x140022473  mov     rcx, r11
0x140022476  call    SkmiBatchFlushSingleTb
0x14002247b  inc     edi
0x14002247d  cmp     edi, 0Bh
0x140022480  jb      loc_1400223AD
0x140022486  cmp     [rsp+158h+var_34], 0
0x14002248e  jz      short loc_1400224A0
0x140022490  mov     cl, [rsp+158h+var_33]
0x140022497  xor     edx, edx
0x140022499  call    SkeFlushEntireTb
0x14002249e  jmp     short loc_1400224C0
0x1400224a0  mov     r8d, [rsp+158h+var_38]
0x1400224a8  test    r8d, r8d
0x1400224ab  jz      short loc_1400224C0
0x1400224ad  mov     cl, [rsp+158h+var_33]
0x1400224b4  lea     r9, [rsp+158h+var_138]
0x1400224b9  xor     edx, edx
0x1400224bb  call    SkeFlushRangeListTb
0x1400224c0  mov     dl, sil
0x1400224c3  lea     rcx, SkmiNteLock
0x1400224ca  call    RtlpReleasePropStoreLockShared
0x1400224cf  add     rsp, 138h
0x1400224d6  pop     rdi
0x1400224d7  pop     rsi
0x1400224d8  pop     rbp
0x1400224d9  pop     rbx
0x1400224da  retn
```
