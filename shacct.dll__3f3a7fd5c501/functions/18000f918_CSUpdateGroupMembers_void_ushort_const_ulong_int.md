# CSUpdateGroupMembers(void *,ushort const * *,ulong,int)

- ea: `0x18000f918`
- end: `0x18000fb2f`
- name: `?CSUpdateGroupMembers@@YAJPEAXPEAPEBGKH@Z`
- size: `535`
- prototype: `int(void *, const unsigned __int16 **, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800126c0`

## callees

- `0x1800059f0`
- `0x18000f918`
- `0x18000fbdc`
- `0x180012f18`
- `0x180013490`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fad2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fae2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fad2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fae2`
- `SAMLIB!SamGetMembersInAlias` at `0x18000f98c`
- `SAMLIB!SamGetMembersInAlias` at `0x18000f98c`
- `SAMLIB!SamRemoveMemberFromAlias` at `0x18000f9cd`
- `SAMLIB!SamRemoveMemberFromAlias` at `0x18000f9cd`
- `SAMLIB!SamAddMemberToAlias` at `0x18000fa37`
- `SAMLIB!SamAddMemberToAlias` at `0x18000fa37`
- `SAMLIB!SamFreeMemory` at `0x18000fa0d`
- `SAMLIB!SamFreeMemory` at `0x18000fa0d`

## pseudocode

```c
__int64 __fastcall CSUpdateGroupMembers(void *a1, const unsigned __int16 **a2, unsigned int a3, int a4)
{
  void *v5; // r14
  int v7; // eax
  unsigned int v8; // ebx
  void **v9; // r13
  int MembersInAlias; // eax
  int v11; // edi
  unsigned int v12; // eax
  __int64 i; // rbp
  void *v14; // r14
  __int64 v15; // r8
  __int64 k; // rdi
  void *v17; // rbp
  __int64 v18; // r8
  int v19; // r14d
  __int64 v20; // r9
  int v21; // ebx
  __int64 j; // rdi
  void *v23; // rcx
  unsigned int v25; // [rsp+30h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-30h] BYREF

  pv = 0;
  v5 = a1;
  v7 = LookupNames((void *)a3, a2, (void ***)&pv);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = (void **)pv;
    if ( a4 )
    {
      pv = 0;
      v25 = 0;
      MembersInAlias = SamGetMembersInAlias(v5, &pv, &v25);
      v11 = MembersInAlias;
      if ( MembersInAlias < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v20 = (unsigned int)MembersInAlias;
          LODWORD(v20) = MembersInAlias | 0x10000000;
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v20);
        }
      }
      else
      {
        v12 = v25;
        if ( v25 )
        {
          for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
          {
            v14 = (void *)*((_QWORD *)pv + i);
            if ( !ContainsSID(v9, a3, v14) )
              v11 = SamRemoveMemberFromAlias(a1, v14);
            if ( v11 < 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF__sid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, v15, v14, v11);
              }
              break;
            }
            v12 = v25;
          }
          SamFreeMemory(pv);
          v5 = a1;
        }
        if ( v11 >= 0 )
          goto LABEL_16;
      }
      v21 = v11;
LABEL_30:
      v8 = v21 | 0x10000000;
LABEL_31:
      for ( j = 0; (unsigned int)j < a3; j = (unsigned int)(j + 1) )
      {
        v23 = v9[j];
        if ( v23 )
          CoTaskMemFree(v23);
      }
      CoTaskMemFree(v9);
      return v8;
    }
LABEL_16:
    for ( k = 0; (unsigned int)k < a3; k = (unsigned int)(k + 1) )
    {
      v17 = v9[k];
      if ( v17 )
      {
        v19 = SamAddMemberToAlias(v5, v9[k]);
        if ( (int)(v19 + 0x80000000) >= 0 && v19 != -1073741485 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF__sid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, v18, v17, v19);
          v21 = v19;
          goto LABEL_30;
        }
      }
      v5 = a1;
    }
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, (unsigned int)v7);
  return v8;
}

```

## disassembly

```asm
0x18000f918  mov     rax, rsp
0x18000f91b  mov     [rax+10h], rbx
0x18000f91f  mov     [rax+18h], rbp
0x18000f923  mov     [rax+8], rcx
0x18000f927  push    rsi
0x18000f928  push    rdi
0x18000f929  push    r12
0x18000f92b  push    r13
0x18000f92d  push    r14
0x18000f92f  sub     rsp, 40h
0x18000f933  mov     r12d, r8d
0x18000f936  mov     qword ptr [rax-30h], 0
0x18000f93e  mov     r14, rcx
0x18000f941  lea     r8, [rax-30h]; void ***
0x18000f945  mov     ecx, r12d; Count
0x18000f948  mov     edi, r9d
0x18000f94b  call    ?LookupNames@@YAJKPEBQEBGPEAPEAPEAX@Z; LookupNames(ulong,ushort const * const *,void * * *)
0x18000f950  lea     rsi, WPP_GLOBAL_Control
0x18000f957  mov     ebx, eax
0x18000f959  test    eax, eax
0x18000f95b  js      loc_18000FAEA
0x18000f961  mov     r13, [rsp+68h+pv]
0x18000f966  test    edi, edi
0x18000f968  jz      loc_18000FA1C
0x18000f96e  lea     r8, [rsp+68h+var_38]
0x18000f973  mov     [rsp+68h+pv], 0
0x18000f97c  lea     rdx, [rsp+68h+pv]
0x18000f981  mov     [rsp+68h+var_38], 0
0x18000f989  mov     rcx, r14
0x18000f98c  call    cs:__imp_SamGetMembersInAlias
0x18000f992  mov     edi, eax
0x18000f994  test    eax, eax
0x18000f996  js      loc_18000FA5F
0x18000f99c  mov     eax, [rsp+68h+var_38]
0x18000f9a0  test    eax, eax
0x18000f9a2  jz      short loc_18000FA18
0x18000f9a4  xor     ebp, ebp
0x18000f9a6  cmp     ebp, eax
0x18000f9a8  jnb     short loc_18000FA08
0x18000f9aa  mov     rax, [rsp+68h+pv]
0x18000f9af  mov     edx, r12d; unsigned int
0x18000f9b2  mov     rcx, r13; void **
0x18000f9b5  mov     r14, [rax+rbp*8]
0x18000f9b9  mov     r8, r14; void *
0x18000f9bc  call    ?ContainsSID@@YAHPEAPEAXKPEAX@Z; ContainsSID(void * *,ulong,void *)
0x18000f9c1  test    eax, eax
0x18000f9c3  jnz     short loc_18000F9D5
0x18000f9c5  mov     rcx, [rsp+68h+arg_0]
0x18000f9ca  mov     rdx, r14
0x18000f9cd  call    cs:__imp_SamRemoveMemberFromAlias
0x18000f9d3  mov     edi, eax
0x18000f9d5  test    edi, edi
0x18000f9d7  js      short loc_18000F9E1
0x18000f9d9  mov     eax, [rsp+68h+var_38]
0x18000f9dd  inc     ebp
0x18000f9df  jmp     short loc_18000F9A6
0x18000f9e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9e8  cmp     rcx, rsi
0x18000f9eb  jz      short loc_18000FA08
0x18000f9ed  test    byte ptr [rcx+1Ch], 4
0x18000f9f1  jz      short loc_18000FA08
0x18000f9f3  mov     rcx, [rcx+10h]
0x18000f9f7  mov     edx, 5Ah ; 'Z'
0x18000f9fc  mov     r9, r14
0x18000f9ff  mov     [rsp+68h+var_48], edi
0x18000fa03  call    WPP_SF__sid_D
0x18000fa08  mov     rcx, [rsp+68h+pv]
0x18000fa0d  call    cs:__imp_SamFreeMemory
0x18000fa13  mov     r14, [rsp+68h+arg_0]
0x18000fa18  test    edi, edi
0x18000fa1a  js      short loc_18000FA8E
0x18000fa1c  xor     edi, edi
0x18000fa1e  cmp     edi, r12d
0x18000fa21  jnb     loc_18000FAC1
0x18000fa27  mov     rbp, [r13+rdi*8+0]
0x18000fa2c  test    rbp, rbp
0x18000fa2f  jz      short loc_18000FA56
0x18000fa31  mov     rdx, rbp
0x18000fa34  mov     rcx, r14
0x18000fa37  call    cs:__imp_SamAddMemberToAlias
0x18000fa3d  mov     r14d, eax
0x18000fa40  mov     eax, 80000000h
0x18000fa45  lea     ecx, [r14+rax]
0x18000fa49  test    eax, ecx
0x18000fa4b  jnz     short loc_18000FA56
0x18000fa4d  cmp     r14d, 0C0000153h
0x18000fa54  jnz     short loc_18000FA92
0x18000fa56  mov     r14, [rsp+68h+arg_0]
0x18000fa5b  inc     edi
0x18000fa5d  jmp     short loc_18000FA1E
0x18000fa5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa66  cmp     rcx, rsi
0x18000fa69  jz      short loc_18000FA8E
0x18000fa6b  test    byte ptr [rcx+1Ch], 2
0x18000fa6f  jz      short loc_18000FA8E
0x18000fa71  mov     rcx, [rcx+10h]
0x18000fa75  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x18000fa7c  mov     r9d, eax
0x18000fa7f  mov     edx, 5Bh ; '['
0x18000fa84  bts     r9d, 1Ch
0x18000fa89  call    WPP_SF_d
0x18000fa8e  mov     ebx, edi
0x18000fa90  jmp     short loc_18000FABD
0x18000fa92  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa99  cmp     rcx, rsi
0x18000fa9c  jz      short loc_18000FABA
0x18000fa9e  test    byte ptr [rcx+1Ch], 4
0x18000faa2  jz      short loc_18000FABA
0x18000faa4  mov     rcx, [rcx+10h]
0x18000faa8  mov     edx, 5Ch ; '\'
0x18000faad  mov     r9, rbp
0x18000fab0  mov     [rsp+68h+var_48], r14d
0x18000fab5  call    WPP_SF__sid_D
0x18000faba  mov     ebx, r14d
0x18000fabd  bts     ebx, 1Ch
0x18000fac1  xor     edi, edi
0x18000fac3  test    r12d, r12d
0x18000fac6  jz      short loc_18000FADF
0x18000fac8  mov     rcx, [r13+rdi*8+0]; pv
0x18000facd  test    rcx, rcx
0x18000fad0  jz      short loc_18000FAD8
0x18000fad2  call    cs:__imp_CoTaskMemFree
0x18000fad8  inc     edi
0x18000fada  cmp     edi, r12d
0x18000fadd  jb      short loc_18000FAC8
0x18000fadf  mov     rcx, r13; pv
0x18000fae2  call    cs:__imp_CoTaskMemFree
0x18000fae8  jmp     short loc_18000FB14
0x18000faea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000faf1  cmp     rcx, rsi
0x18000faf4  jz      short loc_18000FB14
0x18000faf6  test    byte ptr [rcx+1Ch], 2
0x18000fafa  jz      short loc_18000FB14
0x18000fafc  mov     rcx, [rcx+10h]
0x18000fb00  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x18000fb07  mov     edx, 5Dh ; ']'
0x18000fb0c  mov     r9d, eax
0x18000fb0f  call    WPP_SF_d
0x18000fb14  lea     r11, [rsp+68h+var_28]
0x18000fb19  mov     eax, ebx
0x18000fb1b  mov     rbx, [r11+38h]
0x18000fb1f  mov     rbp, [r11+40h]
0x18000fb23  mov     rsp, r11
0x18000fb26  pop     r14
0x18000fb28  pop     r13
0x18000fb2a  pop     r12
0x18000fb2c  pop     rdi
0x18000fb2d  pop     rsi
0x18000fb2e  retn
```
