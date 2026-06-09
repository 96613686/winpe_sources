# SWMRLock::Wake(SWMRLock::RequestorType)

- ea: `0x180017dc0`
- end: `0x180018037`
- name: `?Wake@SWMRLock@@AEAAXW4RequestorType@1@@Z`
- size: `631`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180019288`
- `0x1800c19a0`

## callees

- `0x180017dc0`

## import_xrefs

- `ntdll!NtAlertThreadByThreadId` at `0x180017ef5`
- `ntdll!NtAlertThreadByThreadId` at `0x180017ef5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017e9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017e9f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017de5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017de5`

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
0x180017dc0  push    rbp
0x180017dc2  push    rbx
0x180017dc3  push    rsi
0x180017dc4  push    rdi
0x180017dc5  mov     rbp, rsp
0x180017dc8  sub     rsp, 38h
0x180017dcc  lea     rax, [rbp+var_18]
0x180017dd0  mov     rbx, rcx
0x180017dd3  mov     [rbp+var_10], rax
0x180017dd7  add     rcx, 8; SRWLock
0x180017ddb  lea     rax, [rbp+var_18]
0x180017ddf  mov     edi, edx
0x180017de1  mov     [rbp+var_18], rax
0x180017de5  call    cs:__imp_AcquireSRWLockExclusive
0x180017dec  nop     dword ptr [rax+rax+00h]
0x180017df1  mov     r8d, [rbx]
0x180017df4  test    edi, edi
0x180017df6  jz      loc_180017F10
0x180017dfc  cmp     edi, 1
0x180017dff  jnz     loc_18001801F
0x180017e05  mov     eax, r8d
0x180017e08  and     eax, 3
0x180017e0b  cmp     al, 3
0x180017e0d  jnz     loc_180017FC4
0x180017e13  xor     eax, eax
0x180017e15  lea     r9, [rbx+10h]
0x180017e19  mov     rdx, [r9]
0x180017e1c  cmp     dword ptr [rdx+10h], 0
0x180017e20  jz      loc_180017F7B
0x180017e26  lea     rcx, [rbp+var_18]
0x180017e2a  cmp     [rbp+var_18], rcx
0x180017e2e  jnz     loc_180017F03
0x180017e34  mov     rcx, [rdx]
0x180017e37  cmp     [rcx+8], rdx
0x180017e3b  jnz     loc_180017FD3
0x180017e41  mov     r10, [rdx+8]
0x180017e45  cmp     [r10], rdx
0x180017e48  jnz     loc_180017FD3
0x180017e4e  mov     [r10], rcx
0x180017e51  mov     [rcx+8], r10
0x180017e55  lea     r10, [rbp+var_18]
0x180017e59  mov     rcx, [rbp+var_10]
0x180017e5d  cmp     [rcx], r10
0x180017e60  jnz     loc_180017FD3
0x180017e66  mov     [rdx+8], rcx
0x180017e6a  lea     r10, [rbp+var_18]
0x180017e6e  mov     [rdx], r10
0x180017e71  or      eax, 1
0x180017e74  mov     [rcx], rdx
0x180017e77  mov     [rbp+var_10], rdx
0x180017e7b  mov     ecx, [rdx+14h]
0x180017e7e  mov     [rbx+20h], ecx
0x180017e81  mov     rcx, [r9]
0x180017e84  sub     rcx, r9
0x180017e87  neg     rcx
0x180017e8a  sbb     edx, edx
0x180017e8c  and     eax, 0FFFFFFFDh
0x180017e8f  and     edx, 2
0x180017e92  or      edx, eax
0x180017e94  cmp     edx, r8d
0x180017e97  jz      short loc_180017E9B
0x180017e99  xchg    edx, [rbx]
0x180017e9b  lea     rcx, [rbx+8]; SRWLock
0x180017e9f  call    cs:__imp_ReleaseSRWLockExclusive
0x180017ea6  nop     dword ptr [rax+rax+00h]
0x180017eab  mov     rcx, [rbp+var_18]
0x180017eaf  lea     rax, [rbp+var_18]
0x180017eb3  cmp     rcx, rax
0x180017eb6  jnz     short loc_180017EC2
0x180017eb8  add     rsp, 38h
0x180017ebc  pop     rdi
0x180017ebd  pop     rsi
0x180017ebe  pop     rbx
0x180017ebf  pop     rbp
0x180017ec0  retn
0x180017ec2  lea     rax, [rbp+var_18]
0x180017ec6  cmp     [rcx+8], rax
0x180017eca  jnz     loc_180017FD3
0x180017ed0  mov     rax, [rcx]
0x180017ed3  cmp     [rax+8], rcx
0x180017ed7  jnz     loc_180017FD3
0x180017edd  mov     [rbp+var_18], rax
0x180017ee1  lea     rdx, [rbp+var_18]
0x180017ee5  mov     [rax+8], rdx
0x180017ee9  mov     eax, [rcx+14h]
0x180017eec  mov     dword ptr [rcx+14h], 0
0x180017ef3  mov     ecx, eax
0x180017ef5  call    cs:__imp_NtAlertThreadByThreadId
0x180017efc  nop     dword ptr [rax+rax+00h]
0x180017f01  jmp     short loc_180017EAB
0x180017f03  mov     ecx, eax
0x180017f05  shr     ecx, 2
0x180017f08  mov     [rdx+18h], ecx
0x180017f0b  jmp     loc_180017E81
0x180017f10  lea     r9, [rbx+10h]
0x180017f14  mov     rcx, [r9]
0x180017f17  mov     eax, [rcx+18h]
0x180017f1a  test    eax, eax
0x180017f1c  jle     loc_180017FC4
0x180017f22  sub     eax, 1
0x180017f25  mov     [rcx+18h], eax
0x180017f28  jnz     loc_180017FCB
0x180017f2e  mov     rax, [rcx]
0x180017f31  cmp     [rax+8], rcx
0x180017f35  jnz     loc_180017FD3
0x180017f3b  mov     rdx, [rcx+8]
0x180017f3f  cmp     [rdx], rcx
0x180017f42  jnz     loc_180017FD3
0x180017f48  mov     [rdx], rax
0x180017f4b  mov     [rax+8], rdx
0x180017f4f  lea     rdx, [rbp+var_18]
0x180017f53  mov     rax, [rbp+var_10]
0x180017f57  cmp     [rax], rdx
0x180017f5a  jnz     short loc_180017FD3
0x180017f5c  mov     [rcx+8], rax
0x180017f60  lea     rdx, [rbp+var_18]
0x180017f64  mov     [rcx], rdx
0x180017f67  mov     [rax], rcx
0x180017f6a  mov     eax, 1
0x180017f6f  mov     [rbp+var_10], rcx
0x180017f73  mov     ecx, [rcx+14h]
0x180017f76  jmp     loc_180017E7E
0x180017f7b  mov     rcx, [rdx]
0x180017f7e  cmp     [rcx+8], rdx
0x180017f82  jnz     short loc_180017FD3
0x180017f84  mov     r10, [rdx+8]
0x180017f88  cmp     [r10], rdx
0x180017f8b  jnz     short loc_180017FD3
0x180017f8d  mov     [r10], rcx
0x180017f90  mov     [rcx+8], r10
0x180017f94  lea     r10, [rbp+var_18]
0x180017f98  mov     rcx, [rbp+var_10]
0x180017f9c  cmp     [rcx], r10
0x180017f9f  jnz     short loc_180017FD3
0x180017fa1  mov     [rdx+8], rcx
0x180017fa5  lea     r10, [rbp+var_18]
0x180017fa9  mov     [rdx], r10
0x180017fac  add     eax, 4
0x180017faf  mov     [rcx], rdx
0x180017fb2  mov     [rbp+var_10], rdx
0x180017fb6  cmp     [r9], r9
0x180017fb9  jnz     loc_180017E19
0x180017fbf  jmp     loc_180017E81
0x180017fc4  mov     ecx, 24h ; '$'
0x180017fc9  int     29h; Win8: RtlFailFast(ecx)
0x180017fcb  mov     eax, r8d
0x180017fce  jmp     loc_180017E81
0x180017fd3  mov     ecx, 3
0x180017fd8  int     29h; Win8: RtlFailFast(ecx)
0x180017fda  mov     rcx, [rdx]
0x180017fdd  cmp     [rcx+8], rdx
0x180017fe1  jnz     short loc_180017FD3
0x180017fe3  mov     r10, [rdx+8]
0x180017fe7  cmp     [r10], rdx
0x180017fea  jnz     short loc_180017FD3
0x180017fec  mov     [r10], rcx
0x180017fef  mov     [rcx+8], r10
0x180017ff3  lea     r10, [rbp+var_18]
0x180017ff7  mov     rcx, [rbp+var_10]
0x180017ffb  cmp     [rcx], r10
0x180017ffe  jnz     short loc_180017FD3
0x180018000  mov     [rdx+8], rcx
0x180018004  lea     r10, [rbp+var_18]
0x180018008  mov     [rdx], r10
0x18001800b  add     eax, 4
0x18001800e  mov     [rcx], rdx
0x180018011  mov     [rbp+var_10], rdx
0x180018015  cmp     [r9], r9
0x180018018  jnz     short loc_180018028
0x18001801a  jmp     loc_180017E81
0x18001801f  mov     eax, 4
0x180018024  lea     r9, [rbx+10h]
0x180018028  mov     rdx, [r9]
0x18001802b  cmp     dword ptr [rdx+10h], 0
0x18001802f  jnz     loc_180017F03
0x180018035  jmp     short loc_180017FDA
```
