# SWMRLock::Wake(SWMRLock::RequestorType)

- ea: `0x180016858`
- end: `0x180016ab9`
- name: `?Wake@SWMRLock@@AEAAXW4RequestorType@1@@Z`
- size: `609`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180017b14`
- `0x1800bd220`

## callees

- `0x180016858`

## import_xrefs

- `ntdll!NtAlertThreadByThreadId` at `0x180016980`
- `ntdll!NtAlertThreadByThreadId` at `0x180016980`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016931`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016931`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001687d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001687d`

## pseudocode

```c
__int64 **__fastcall SWMRLock::Wake(__int64 a1, int a2)
{
  volatile __int32 v4; // r8d
  unsigned int v5; // eax
  __int64 ****v6; // r9
  __int64 ***v7; // rdx
  __int64 **v8; // rcx
  __int64 ****v9; // r10
  _QWORD *v10; // rcx
  int v11; // ecx
  unsigned int v12; // edx
  __int64 *v13; // rcx
  __int64 **result; // rax
  __int64 *v15; // rax
  unsigned int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  __int64 *v20; // rax
  __int64 **v21; // rdx
  __int64 **v22; // rax
  __int64 **v23; // rcx
  __int64 ****v24; // r10
  _QWORD *v25; // rcx
  __int64 **v26; // rcx
  __int64 ****v27; // r10
  _QWORD *v28; // rcx
  __int64 *v29; // [rsp+20h] [rbp-18h] BYREF
  __int64 **v30; // [rsp+28h] [rbp-10h]

  v30 = &v29;
  v29 = (__int64 *)&v29;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
  v4 = *(_DWORD *)a1;
  if ( !a2 )
  {
    v6 = (__int64 ****)(a1 + 16);
    v17 = *(_QWORD *)(a1 + 16);
    v18 = *(_DWORD *)(v17 + 24);
    if ( v18 > 0 )
    {
      v19 = v18 - 1;
      *(_DWORD *)(v17 + 24) = v19;
      if ( v19 )
      {
        v5 = v4;
        goto LABEL_12;
      }
      v20 = *(__int64 **)v17;
      if ( *(_QWORD *)(*(_QWORD *)v17 + 8LL) == v17 )
      {
        v21 = *(__int64 ***)(v17 + 8);
        if ( *v21 == (__int64 *)v17 )
        {
          *v21 = v20;
          v20[1] = (__int64)v21;
          v22 = v30;
          if ( *v30 == (__int64 *)&v29 )
          {
            *(_QWORD *)(v17 + 8) = v30;
            *(_QWORD *)v17 = &v29;
            *v22 = (__int64 *)v17;
            v5 = 1;
            v30 = (__int64 **)v17;
            v11 = *(_DWORD *)(v17 + 20);
            goto LABEL_11;
          }
        }
      }
LABEL_33:
      __fastfail(3u);
    }
    goto LABEL_31;
  }
  if ( a2 != 1 )
  {
    v5 = 4;
    v6 = (__int64 ****)(a1 + 16);
    while ( 1 )
    {
      v7 = *v6;
      if ( *((_DWORD *)*v6 + 4) )
        goto LABEL_19;
      v26 = *v7;
      if ( (*v7)[1] != (__int64 *)v7 )
        goto LABEL_33;
      v27 = (__int64 ****)v7[1];
      if ( *v27 != v7 )
        goto LABEL_33;
      *v27 = (__int64 ***)v26;
      v26[1] = (__int64 *)v27;
      v28 = v30;
      if ( *v30 != (__int64 *)&v29 )
        goto LABEL_33;
      v7[1] = v30;
      *v7 = &v29;
      v5 += 4;
      *v28 = v7;
      v30 = (__int64 **)v7;
      if ( *v6 == (__int64 ***)v6 )
        goto LABEL_12;
    }
  }
  if ( (v4 & 3) != 3 )
LABEL_31:
    __fastfail(0x24u);
  v5 = 0;
  v6 = (__int64 ****)(a1 + 16);
  while ( 1 )
  {
    v7 = *v6;
    if ( *((_DWORD *)*v6 + 4) )
      break;
    v23 = *v7;
    if ( (*v7)[1] != (__int64 *)v7 )
      goto LABEL_33;
    v24 = (__int64 ****)v7[1];
    if ( *v24 != v7 )
      goto LABEL_33;
    *v24 = (__int64 ***)v23;
    v23[1] = (__int64 *)v24;
    v25 = v30;
    if ( *v30 != (__int64 *)&v29 )
      goto LABEL_33;
    v7[1] = v30;
    *v7 = &v29;
    v5 += 4;
    *v25 = v7;
    v30 = (__int64 **)v7;
    if ( *v6 == (__int64 ***)v6 )
      goto LABEL_12;
  }
  if ( v29 != (__int64 *)&v29 )
  {
LABEL_19:
    *((_DWORD *)v7 + 6) = v5 >> 2;
    goto LABEL_12;
  }
  v8 = *v7;
  if ( (*v7)[1] != (__int64 *)v7 )
    goto LABEL_33;
  v9 = (__int64 ****)v7[1];
  if ( *v9 != v7 )
    goto LABEL_33;
  *v9 = (__int64 ***)v8;
  v8[1] = (__int64 *)v9;
  v10 = v30;
  if ( *v30 != (__int64 *)&v29 )
    goto LABEL_33;
  v7[1] = v30;
  *v7 = &v29;
  v5 |= 1u;
  *v10 = v7;
  v30 = (__int64 **)v7;
  v11 = *((_DWORD *)v7 + 5);
LABEL_11:
  *(_DWORD *)(a1 + 32) = v11;
LABEL_12:
  v12 = v5 & 0xFFFFFFFD | (v6 != (__int64 ****)*v6 ? 2 : 0);
  if ( v12 != v4 )
    _InterlockedExchange((volatile __int32 *)a1, v12);
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 8));
  while ( 1 )
  {
    v13 = v29;
    result = &v29;
    if ( v29 == (__int64 *)&v29 )
      return result;
    if ( (__int64 **)v29[1] != &v29 )
      goto LABEL_33;
    v15 = (__int64 *)*v29;
    if ( *(__int64 **)(*v29 + 8) != v29 )
      goto LABEL_33;
    v29 = (__int64 *)*v29;
    v15[1] = (__int64)&v29;
    v16 = *((_DWORD *)v13 + 5);
    *((_DWORD *)v13 + 5) = 0;
    NtAlertThreadByThreadId(v16);
  }
}

```

## disassembly

```asm
0x180016858  push    rbp
0x18001685a  push    rbx
0x18001685b  push    rsi
0x18001685c  push    rdi
0x18001685d  mov     rbp, rsp
0x180016860  sub     rsp, 38h
0x180016864  lea     rax, [rbp+var_18]
0x180016868  mov     rbx, rcx
0x18001686b  mov     [rbp+var_10], rax
0x18001686f  add     rcx, 8; SRWLock
0x180016873  lea     rax, [rbp+var_18]
0x180016877  mov     edi, edx
0x180016879  mov     [rbp+var_18], rax
0x18001687d  call    cs:__imp_AcquireSRWLockExclusive
0x180016883  mov     r8d, [rbx]
0x180016886  test    edi, edi
0x180016888  jz      loc_180016992
0x18001688e  cmp     edi, 1
0x180016891  jnz     loc_180016AA1
0x180016897  mov     eax, r8d
0x18001689a  and     eax, 3
0x18001689d  cmp     al, 3
0x18001689f  jnz     loc_180016A46
0x1800168a5  xor     eax, eax
0x1800168a7  lea     r9, [rbx+10h]
0x1800168ab  mov     rdx, [r9]
0x1800168ae  cmp     dword ptr [rdx+10h], 0
0x1800168b2  jz      loc_1800169FD
0x1800168b8  lea     rcx, [rbp+var_18]
0x1800168bc  cmp     [rbp+var_18], rcx
0x1800168c0  jnz     loc_180016988
0x1800168c6  mov     rcx, [rdx]
0x1800168c9  cmp     [rcx+8], rdx
0x1800168cd  jnz     loc_180016A55
0x1800168d3  mov     r10, [rdx+8]
0x1800168d7  cmp     [r10], rdx
0x1800168da  jnz     loc_180016A55
0x1800168e0  mov     [r10], rcx
0x1800168e3  mov     [rcx+8], r10
0x1800168e7  lea     r10, [rbp+var_18]
0x1800168eb  mov     rcx, [rbp+var_10]
0x1800168ef  cmp     [rcx], r10
0x1800168f2  jnz     loc_180016A55
0x1800168f8  mov     [rdx+8], rcx
0x1800168fc  lea     r10, [rbp+var_18]
0x180016900  mov     [rdx], r10
0x180016903  or      eax, 1
0x180016906  mov     [rcx], rdx
0x180016909  mov     [rbp+var_10], rdx
0x18001690d  mov     ecx, [rdx+14h]
0x180016910  mov     [rbx+20h], ecx
0x180016913  mov     rcx, [r9]
0x180016916  sub     rcx, r9
0x180016919  neg     rcx
0x18001691c  sbb     edx, edx
0x18001691e  and     eax, 0FFFFFFFDh
0x180016921  and     edx, 2
0x180016924  or      edx, eax
0x180016926  cmp     edx, r8d
0x180016929  jz      short loc_18001692D
0x18001692b  xchg    edx, [rbx]
0x18001692d  lea     rcx, [rbx+8]; SRWLock
0x180016931  call    cs:__imp_ReleaseSRWLockExclusive
0x180016937  mov     rcx, [rbp+var_18]
0x18001693b  lea     rax, [rbp+var_18]
0x18001693f  cmp     rcx, rax
0x180016942  jnz     short loc_18001694D
0x180016944  add     rsp, 38h
0x180016948  pop     rdi
0x180016949  pop     rsi
0x18001694a  pop     rbx
0x18001694b  pop     rbp
0x18001694c  retn
0x18001694d  lea     rax, [rbp+var_18]
0x180016951  cmp     [rcx+8], rax
0x180016955  jnz     loc_180016A55
0x18001695b  mov     rax, [rcx]
0x18001695e  cmp     [rax+8], rcx
0x180016962  jnz     loc_180016A55
0x180016968  mov     [rbp+var_18], rax
0x18001696c  lea     rdx, [rbp+var_18]
0x180016970  mov     [rax+8], rdx
0x180016974  mov     eax, [rcx+14h]
0x180016977  mov     dword ptr [rcx+14h], 0
0x18001697e  mov     ecx, eax
0x180016980  call    cs:__imp_NtAlertThreadByThreadId
0x180016986  jmp     short loc_180016937
0x180016988  mov     ecx, eax
0x18001698a  shr     ecx, 2
0x18001698d  mov     [rdx+18h], ecx
0x180016990  jmp     short loc_180016913
0x180016992  lea     r9, [rbx+10h]
0x180016996  mov     rcx, [r9]
0x180016999  mov     eax, [rcx+18h]
0x18001699c  test    eax, eax
0x18001699e  jle     loc_180016A46
0x1800169a4  sub     eax, 1
0x1800169a7  mov     [rcx+18h], eax
0x1800169aa  jnz     loc_180016A4D
0x1800169b0  mov     rax, [rcx]
0x1800169b3  cmp     [rax+8], rcx
0x1800169b7  jnz     loc_180016A55
0x1800169bd  mov     rdx, [rcx+8]
0x1800169c1  cmp     [rdx], rcx
0x1800169c4  jnz     loc_180016A55
0x1800169ca  mov     [rdx], rax
0x1800169cd  mov     [rax+8], rdx
0x1800169d1  lea     rdx, [rbp+var_18]
0x1800169d5  mov     rax, [rbp+var_10]
0x1800169d9  cmp     [rax], rdx
0x1800169dc  jnz     short loc_180016A55
0x1800169de  mov     [rcx+8], rax
0x1800169e2  lea     rdx, [rbp+var_18]
0x1800169e6  mov     [rcx], rdx
0x1800169e9  mov     [rax], rcx
0x1800169ec  mov     eax, 1
0x1800169f1  mov     [rbp+var_10], rcx
0x1800169f5  mov     ecx, [rcx+14h]
0x1800169f8  jmp     loc_180016910
0x1800169fd  mov     rcx, [rdx]
0x180016a00  cmp     [rcx+8], rdx
0x180016a04  jnz     short loc_180016A55
0x180016a06  mov     r10, [rdx+8]
0x180016a0a  cmp     [r10], rdx
0x180016a0d  jnz     short loc_180016A55
0x180016a0f  mov     [r10], rcx
0x180016a12  mov     [rcx+8], r10
0x180016a16  lea     r10, [rbp+var_18]
0x180016a1a  mov     rcx, [rbp+var_10]
0x180016a1e  cmp     [rcx], r10
0x180016a21  jnz     short loc_180016A55
0x180016a23  mov     [rdx+8], rcx
0x180016a27  lea     r10, [rbp+var_18]
0x180016a2b  mov     [rdx], r10
0x180016a2e  add     eax, 4
0x180016a31  mov     [rcx], rdx
0x180016a34  mov     [rbp+var_10], rdx
0x180016a38  cmp     [r9], r9
0x180016a3b  jnz     loc_1800168AB
0x180016a41  jmp     loc_180016913
0x180016a46  mov     ecx, 24h ; '$'
0x180016a4b  int     29h; Win8: RtlFailFast(ecx)
0x180016a4d  mov     eax, r8d
0x180016a50  jmp     loc_180016913
0x180016a55  mov     ecx, 3
0x180016a5a  int     29h; Win8: RtlFailFast(ecx)
0x180016a5c  mov     rcx, [rdx]
0x180016a5f  cmp     [rcx+8], rdx
0x180016a63  jnz     short loc_180016A55
0x180016a65  mov     r10, [rdx+8]
0x180016a69  cmp     [r10], rdx
0x180016a6c  jnz     short loc_180016A55
0x180016a6e  mov     [r10], rcx
0x180016a71  mov     [rcx+8], r10
0x180016a75  lea     r10, [rbp+var_18]
0x180016a79  mov     rcx, [rbp+var_10]
0x180016a7d  cmp     [rcx], r10
0x180016a80  jnz     short loc_180016A55
0x180016a82  mov     [rdx+8], rcx
0x180016a86  lea     r10, [rbp+var_18]
0x180016a8a  mov     [rdx], r10
0x180016a8d  add     eax, 4
0x180016a90  mov     [rcx], rdx
0x180016a93  mov     [rbp+var_10], rdx
0x180016a97  cmp     [r9], r9
0x180016a9a  jnz     short loc_180016AAA
0x180016a9c  jmp     loc_180016913
0x180016aa1  mov     eax, 4
0x180016aa6  lea     r9, [rbx+10h]
0x180016aaa  mov     rdx, [r9]
0x180016aad  cmp     dword ptr [rdx+10h], 0
0x180016ab1  jnz     loc_180016988
0x180016ab7  jmp     short loc_180016A5C
```
