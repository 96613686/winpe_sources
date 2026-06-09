# SWMRLock::Wait(SWMRLock::RequestorType)

- ea: `0x18008bd34`
- end: `0x18008bf7a`
- name: `?Wait@SWMRLock@@AEAAJW4RequestorType@1@@Z`
- size: `582`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005cd0`
- `0x180009f70`

## callees

- `0x18008bd34`

## import_xrefs

- `ntdll!NtWaitForAlertByThreadId` at `0x18008be16`
- `ntdll!NtWaitForAlertByThreadId` at `0x18008be16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008be05`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008be4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008be96`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008bf3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008be05`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008be4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008be96`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008bf3f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008bd63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008bd63`

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
0x18008bd34  push    rbp
0x18008bd36  push    rbx
0x18008bd37  push    rsi
0x18008bd38  push    rdi
0x18008bd39  mov     rbp, rsp
0x18008bd3c  sub     rsp, 48h
0x18008bd40  mov     [rbp+var_18], edx
0x18008bd43  lea     rsi, [rcx+8]
0x18008bd47  mov     rax, gs:48h
0x18008bd50  mov     rbx, rcx
0x18008bd53  mov     rcx, rsi; SRWLock
0x18008bd56  mov     [rbp+var_14], eax
0x18008bd59  mov     edi, edx
0x18008bd5b  mov     [rbp+var_10], 0
0x18008bd63  call    cs:__imp_AcquireSRWLockExclusive
0x18008bd6a  nop     dword ptr [rax+rax+00h]
0x18008bd6f  mov     r8d, [rbx]
0x18008bd72  mov     r11d, 1
0x18008bd78  lea     r10d, [r11+1]
0x18008bd7c  lea     r9d, [r11+2]
0x18008bd80  mov     ecx, edi
0x18008bd82  test    edi, edi
0x18008bd84  jz      loc_18008BEB1
0x18008bd8a  sub     ecx, r11d
0x18008bd8d  jnz     loc_18008BE35
0x18008bd93  mov     eax, r8d
0x18008bd96  neg     eax
0x18008bd98  sbb     ecx, ecx
0x18008bd9a  neg     ecx
0x18008bd9c  add     ecx, r11d
0x18008bd9f  or      ecx, r8d
0x18008bda2  cmp     ecx, r8d
0x18008bda5  jz      short loc_18008BDB4
0x18008bda7  mov     eax, r8d
0x18008bdaa  lock cmpxchg [rbx], ecx
0x18008bdae  jnz     loc_18008BF06
0x18008bdb4  test    r10b, cl
0x18008bdb7  jz      loc_18008BE93
0x18008bdbd  test    r10b, r8b
0x18008bdc0  setz    cl
0x18008bdc3  test    r11b, r8b
0x18008bdc6  setz    al
0x18008bdc9  test    al, cl
0x18008bdcb  jnz     loc_18008BE5D
0x18008bdd1  lea     rcx, [rbx+10h]
0x18008bdd5  cmp     edi, r10d
0x18008bdd8  jz      loc_18008BE79
0x18008bdde  mov     rax, [rcx+8]
0x18008bde2  cmp     [rax], rcx
0x18008bde5  jnz     loc_18008BE8E
0x18008bdeb  mov     [rbp+var_20], rax
0x18008bdef  lea     rdx, [rbp+var_28]
0x18008bdf3  mov     [rbp+var_28], rcx
0x18008bdf7  mov     [rax], rdx
0x18008bdfa  lea     rax, [rbp+var_28]
0x18008bdfe  mov     [rcx+8], rax
0x18008be02  mov     rcx, rsi; SRWLock
0x18008be05  call    cs:__imp_ReleaseSRWLockExclusive
0x18008be0c  nop     dword ptr [rax+rax+00h]
0x18008be11  xor     edx, edx
0x18008be13  mov     rcx, rbx
0x18008be16  call    cs:__imp_NtWaitForAlertByThreadId
0x18008be1d  nop     dword ptr [rax+rax+00h]
0x18008be22  cmp     [rbp+var_14], 0
0x18008be26  jnz     short loc_18008BE11
0x18008be28  mov     eax, dword ptr [rbp+var_10+4]
0x18008be2b  add     rsp, 48h
0x18008be2f  pop     rdi
0x18008be30  pop     rsi
0x18008be31  pop     rbx
0x18008be32  pop     rbp
0x18008be33  retn
0x18008be35  cmp     ecx, r11d
0x18008be38  jnz     loc_18008BF50
0x18008be3e  test    r11b, r8b
0x18008be41  jz      loc_18008BEDD
0x18008be47  mov     rcx, rsi; SRWLock
0x18008be4a  call    cs:__imp_ReleaseSRWLockExclusive
0x18008be51  nop     dword ptr [rax+rax+00h]
0x18008be56  mov     eax, 6E4h
0x18008be5b  jmp     short loc_18008BE2B
0x18008be5d  shr     r8d, 2
0x18008be61  mov     dword ptr [rbp+var_10], r8d
0x18008be65  cmp     edi, r10d
0x18008be68  jnz     loc_18008BDD1
0x18008be6e  dec     r8d
0x18008be71  lea     rcx, [rbx+10h]
0x18008be75  mov     dword ptr [rbp+var_10], r8d
0x18008be79  mov     rdx, [rcx]
0x18008be7c  cmp     rdx, rcx
0x18008be7f  jnz     loc_18008BF57
0x18008be85  mov     rax, [rcx]
0x18008be88  cmp     [rax+8], rcx
0x18008be8c  jz      short loc_18008BEC1
0x18008be8e  mov     rcx, r9
0x18008be91  int     29h; Win8: RtlFailFast(ecx)
0x18008be93  mov     rcx, rsi; SRWLock
0x18008be96  call    cs:__imp_ReleaseSRWLockExclusive
0x18008be9d  nop     dword ptr [rax+rax+00h]
0x18008bea2  test    edi, edi
0x18008bea4  jz      short loc_18008BE28
0x18008bea6  mov     eax, [rbp+var_14]
0x18008bea9  mov     [rbx+20h], eax
0x18008beac  jmp     loc_18008BE28
0x18008beb1  test    r9b, r8b
0x18008beb4  jz      short loc_18008BEFD
0x18008beb6  mov     ecx, r8d
0x18008beb9  or      ecx, r10d
0x18008bebc  jmp     loc_18008BDA2
0x18008bec1  mov     [rbp+var_28], rax
0x18008bec5  lea     rdx, [rbp+var_28]
0x18008bec9  mov     [rbp+var_20], rcx
0x18008becd  mov     [rax+8], rdx
0x18008bed1  lea     rax, [rbp+var_28]
0x18008bed5  mov     [rcx], rax
0x18008bed8  jmp     loc_18008BE02
0x18008bedd  test    r10b, r8b
0x18008bee0  jnz     short loc_18008BF0E
0x18008bee2  mov     eax, r8d
0x18008bee5  shr     eax, 2
0x18008bee8  cmp     eax, r11d
0x18008beeb  jnz     short loc_18008BEF5
0x18008beed  mov     ecx, r11d
0x18008bef0  jmp     loc_18008BDA2
0x18008bef5  jbe     loc_18008BE47
0x18008befb  jmp     short loc_18008BEB6
0x18008befd  lea     ecx, [r8+4]
0x18008bf01  jmp     loc_18008BDA2
0x18008bf06  mov     r8d, eax
0x18008bf09  jmp     loc_18008BD80
0x18008bf0e  mov     rdx, [rbx+10h]
0x18008bf12  mov     eax, [rdx+18h]
0x18008bf15  test    eax, eax
0x18008bf17  jz      loc_18008BE47
0x18008bf1d  sub     eax, r11d
0x18008bf20  mov     ecx, r8d
0x18008bf23  mov     [rdx+18h], eax
0x18008bf26  jnz     loc_18008BDB4
0x18008bf2c  xchg    r9d, [rbx]
0x18008bf2f  cmp     [rdx+10h], r10d
0x18008bf33  jnz     short loc_18008BF3C
0x18008bf35  mov     dword ptr [rdx+1Ch], 460h
0x18008bf3c  mov     rcx, rsi; SRWLock
0x18008bf3f  call    cs:__imp_ReleaseSRWLockExclusive
0x18008bf46  nop     dword ptr [rax+rax+00h]
0x18008bf4b  jmp     loc_18008BEA6
0x18008bf50  mov     ecx, 5
0x18008bf55  int     29h; Win8: RtlFailFast(ecx)
0x18008bf57  mov     eax, [rdx+18h]
0x18008bf5a  mov     dword ptr [rbp+var_10], eax
0x18008bf5d  mov     dword ptr [rdx+18h], 0
0x18008bf64  cmp     [rdx+10h], r10d
0x18008bf68  jnz     loc_18008BE85
0x18008bf6e  mov     dword ptr [rdx+1Ch], 460h
0x18008bf75  jmp     loc_18008BE85
```
