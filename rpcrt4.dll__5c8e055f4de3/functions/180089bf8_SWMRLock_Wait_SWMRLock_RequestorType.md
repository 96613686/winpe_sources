# SWMRLock::Wait(SWMRLock::RequestorType)

- ea: `0x180089bf8`
- end: `0x180089e12`
- name: `?Wait@SWMRLock@@AEAAJW4RequestorType@1@@Z`
- size: `538`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180065a10`
- `0x180069cc0`

## callees

- `0x180089bf8`

## import_xrefs

- `ntdll!NtWaitForAlertByThreadId` at `0x180089cca`
- `ntdll!NtWaitForAlertByThreadId` at `0x180089cca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180089cbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180089cf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180089d3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180089ddd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180089cbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180089cf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180089d3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180089ddd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180089c27`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180089c27`

## pseudocode

```c
__int64 __fastcall SWMRLock::Wait(__int64 a1, int a2)
{
  RTL_SRWLOCK *v2; // rsi
  unsigned __int32 i; // r8d
  signed __int32 v6; // ecx
  signed __int32 v7; // eax
  __int64 *v8; // rcx
  __int64 **v9; // rax
  unsigned __int32 v11; // r8d
  __int64 *v12; // rdx
  _DWORD *v13; // rax
  _DWORD *v14; // rdx
  int v15; // eax
  int v16; // eax
  __int64 v17; // [rsp+20h] [rbp-28h] BYREF
  __int64 *v18; // [rsp+28h] [rbp-20h]
  int v19; // [rsp+30h] [rbp-18h]
  int UniqueThread; // [rsp+34h] [rbp-14h]
  __int64 v21; // [rsp+38h] [rbp-10h]

  v19 = a2;
  v2 = (RTL_SRWLOCK *)(a1 + 8);
  UniqueThread = (int)NtCurrentTeb()->ClientId.UniqueThread;
  v21 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
  for ( i = *(_DWORD *)a1; ; i = v7 )
  {
    if ( !a2 )
    {
      if ( (i & 3) == 0 )
      {
        v6 = i + 4;
        goto LABEL_5;
      }
LABEL_26:
      v6 = i | 2;
      goto LABEL_5;
    }
    if ( a2 != 1 )
      break;
    v6 = i | ((i != 0) + 1);
LABEL_5:
    if ( v6 != i )
    {
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v6, i);
      if ( i != v7 )
        continue;
    }
    goto LABEL_7;
  }
  if ( a2 != 2 )
    __fastfail(5u);
  if ( (i & 1) != 0 )
    goto LABEL_17;
  if ( (i & 2) == 0 )
  {
    if ( i >> 2 == 1 )
    {
      v6 = 1;
      goto LABEL_5;
    }
    if ( i >> 2 <= 1 )
      goto LABEL_17;
    goto LABEL_26;
  }
  v14 = *(_DWORD **)(a1 + 16);
  v15 = v14[6];
  if ( !v15 )
  {
LABEL_17:
    ReleaseSRWLockExclusive(v2);
    return 1764;
  }
  v16 = v15 - 1;
  LOBYTE(v6) = i;
  v14[6] = v16;
  if ( v16 )
  {
LABEL_7:
    if ( (v6 & 2) == 0 )
    {
      ReleaseSRWLockExclusive(v2);
      if ( a2 )
        goto LABEL_24;
      return HIDWORD(v21);
    }
    if ( (i & 2) == 0 && (i & 1) == 0 && (v11 = i >> 2, LODWORD(v21) = v11, a2 == 2) )
    {
      v8 = (__int64 *)(a1 + 16);
      LODWORD(v21) = v11 - 1;
    }
    else
    {
      v8 = (__int64 *)(a1 + 16);
      if ( a2 != 2 )
      {
        v9 = *(__int64 ***)(a1 + 24);
        if ( *v9 != v8 )
          goto LABEL_22;
        v18 = *(__int64 **)(a1 + 24);
        v17 = a1 + 16;
        *v9 = &v17;
        *(_QWORD *)(a1 + 24) = &v17;
        goto LABEL_12;
      }
    }
    v12 = (__int64 *)*v8;
    if ( (__int64 *)*v8 != v8 )
    {
      LODWORD(v21) = *((_DWORD *)v12 + 6);
      *((_DWORD *)v12 + 6) = 0;
      if ( *((_DWORD *)v12 + 4) == 2 )
        *((_DWORD *)v12 + 7) = 1120;
    }
    v13 = (_DWORD *)*v8;
    if ( *(__int64 **)(*v8 + 8) != v8 )
LABEL_22:
      __fastfail(3u);
    v17 = *v8;
    v18 = v8;
    *((_QWORD *)v13 + 1) = &v17;
    *v8 = (__int64)&v17;
LABEL_12:
    ReleaseSRWLockExclusive(v2);
    do
      NtWaitForAlertByThreadId(a1, 0);
    while ( UniqueThread );
    return HIDWORD(v21);
  }
  _InterlockedExchange((volatile __int32 *)a1, 3);
  if ( v14[4] == 2 )
    v14[7] = 1120;
  ReleaseSRWLockExclusive(v2);
LABEL_24:
  *(_DWORD *)(a1 + 32) = UniqueThread;
  return HIDWORD(v21);
}

```

## disassembly

```asm
0x180089bf8  push    rbp
0x180089bfa  push    rbx
0x180089bfb  push    rsi
0x180089bfc  push    rdi
0x180089bfd  mov     rbp, rsp
0x180089c00  sub     rsp, 48h
0x180089c04  mov     [rbp+var_18], edx
0x180089c07  lea     rsi, [rcx+8]
0x180089c0b  mov     rax, gs:48h
0x180089c14  mov     rbx, rcx
0x180089c17  mov     rcx, rsi; SRWLock
0x180089c1a  mov     [rbp+var_14], eax
0x180089c1d  mov     edi, edx
0x180089c1f  mov     [rbp+var_10], 0
0x180089c27  call    cs:__imp_AcquireSRWLockExclusive
0x180089c2d  mov     r8d, [rbx]
0x180089c30  mov     r11d, 1
0x180089c36  lea     r10d, [r11+1]
0x180089c3a  lea     r9d, [r11+2]
0x180089c3e  mov     ecx, edi
0x180089c40  test    edi, edi
0x180089c42  jz      loc_180089D4F
0x180089c48  sub     ecx, r11d
0x180089c4b  jnz     loc_180089CE2
0x180089c51  mov     eax, r8d
0x180089c54  neg     eax
0x180089c56  sbb     ecx, ecx
0x180089c58  neg     ecx
0x180089c5a  add     ecx, r11d
0x180089c5d  or      ecx, r8d
0x180089c60  cmp     ecx, r8d
0x180089c63  jz      short loc_180089C72
0x180089c65  mov     eax, r8d
0x180089c68  lock cmpxchg [rbx], ecx
0x180089c6c  jnz     loc_180089DA4
0x180089c72  test    r10b, cl
0x180089c75  jz      loc_180089D3A
0x180089c7b  test    r10b, r8b
0x180089c7e  setz    cl
0x180089c81  test    r11b, r8b
0x180089c84  setz    al
0x180089c87  test    al, cl
0x180089c89  jnz     short loc_180089D04
0x180089c8b  lea     rcx, [rbx+10h]
0x180089c8f  cmp     edi, r10d
0x180089c92  jz      loc_180089D20
0x180089c98  mov     rax, [rcx+8]
0x180089c9c  cmp     [rax], rcx
0x180089c9f  jnz     loc_180089D35
0x180089ca5  mov     [rbp+var_20], rax
0x180089ca9  lea     rdx, [rbp+var_28]
0x180089cad  mov     [rbp+var_28], rcx
0x180089cb1  mov     [rax], rdx
0x180089cb4  lea     rax, [rbp+var_28]
0x180089cb8  mov     [rcx+8], rax
0x180089cbc  mov     rcx, rsi; SRWLock
0x180089cbf  call    cs:__imp_ReleaseSRWLockExclusive
0x180089cc5  xor     edx, edx
0x180089cc7  mov     rcx, rbx
0x180089cca  call    cs:__imp_NtWaitForAlertByThreadId
0x180089cd0  cmp     [rbp+var_14], 0
0x180089cd4  jnz     short loc_180089CC5
0x180089cd6  mov     eax, dword ptr [rbp+var_10+4]
0x180089cd9  add     rsp, 48h
0x180089cdd  pop     rdi
0x180089cde  pop     rsi
0x180089cdf  pop     rbx
0x180089ce0  pop     rbp
0x180089ce1  retn
0x180089ce2  cmp     ecx, r11d
0x180089ce5  jnz     loc_180089DE8
0x180089ceb  test    r11b, r8b
0x180089cee  jz      loc_180089D7B
0x180089cf4  mov     rcx, rsi; SRWLock
0x180089cf7  call    cs:__imp_ReleaseSRWLockExclusive
0x180089cfd  mov     eax, 6E4h
0x180089d02  jmp     short loc_180089CD9
0x180089d04  shr     r8d, 2
0x180089d08  mov     dword ptr [rbp+var_10], r8d
0x180089d0c  cmp     edi, r10d
0x180089d0f  jnz     loc_180089C8B
0x180089d15  dec     r8d
0x180089d18  lea     rcx, [rbx+10h]
0x180089d1c  mov     dword ptr [rbp+var_10], r8d
0x180089d20  mov     rdx, [rcx]
0x180089d23  cmp     rdx, rcx
0x180089d26  jnz     loc_180089DEF
0x180089d2c  mov     rax, [rcx]
0x180089d2f  cmp     [rax+8], rcx
0x180089d33  jz      short loc_180089D5F
0x180089d35  mov     rcx, r9
0x180089d38  int     29h; Win8: RtlFailFast(ecx)
0x180089d3a  mov     rcx, rsi; SRWLock
0x180089d3d  call    cs:__imp_ReleaseSRWLockExclusive
0x180089d43  test    edi, edi
0x180089d45  jz      short loc_180089CD6
0x180089d47  mov     eax, [rbp+var_14]
0x180089d4a  mov     [rbx+20h], eax
0x180089d4d  jmp     short loc_180089CD6
0x180089d4f  test    r9b, r8b
0x180089d52  jz      short loc_180089D9B
0x180089d54  mov     ecx, r8d
0x180089d57  or      ecx, r10d
0x180089d5a  jmp     loc_180089C60
0x180089d5f  mov     [rbp+var_28], rax
0x180089d63  lea     rdx, [rbp+var_28]
0x180089d67  mov     [rbp+var_20], rcx
0x180089d6b  mov     [rax+8], rdx
0x180089d6f  lea     rax, [rbp+var_28]
0x180089d73  mov     [rcx], rax
0x180089d76  jmp     loc_180089CBC
0x180089d7b  test    r10b, r8b
0x180089d7e  jnz     short loc_180089DAC
0x180089d80  mov     eax, r8d
0x180089d83  shr     eax, 2
0x180089d86  cmp     eax, r11d
0x180089d89  jnz     short loc_180089D93
0x180089d8b  mov     ecx, r11d
0x180089d8e  jmp     loc_180089C60
0x180089d93  jbe     loc_180089CF4
0x180089d99  jmp     short loc_180089D54
0x180089d9b  lea     ecx, [r8+4]
0x180089d9f  jmp     loc_180089C60
0x180089da4  mov     r8d, eax
0x180089da7  jmp     loc_180089C3E
0x180089dac  mov     rdx, [rbx+10h]
0x180089db0  mov     eax, [rdx+18h]
0x180089db3  test    eax, eax
0x180089db5  jz      loc_180089CF4
0x180089dbb  sub     eax, r11d
0x180089dbe  mov     ecx, r8d
0x180089dc1  mov     [rdx+18h], eax
0x180089dc4  jnz     loc_180089C72
0x180089dca  xchg    r9d, [rbx]
0x180089dcd  cmp     [rdx+10h], r10d
0x180089dd1  jnz     short loc_180089DDA
0x180089dd3  mov     dword ptr [rdx+1Ch], 460h
0x180089dda  mov     rcx, rsi; SRWLock
0x180089ddd  call    cs:__imp_ReleaseSRWLockExclusive
0x180089de3  jmp     loc_180089D47
0x180089de8  mov     ecx, 5
0x180089ded  int     29h; Win8: RtlFailFast(ecx)
0x180089def  mov     eax, [rdx+18h]
0x180089df2  mov     dword ptr [rbp+var_10], eax
0x180089df5  mov     dword ptr [rdx+18h], 0
0x180089dfc  cmp     [rdx+10h], r10d
0x180089e00  jnz     loc_180089D2C
0x180089e06  mov     dword ptr [rdx+1Ch], 460h
0x180089e0d  jmp     loc_180089D2C
```
