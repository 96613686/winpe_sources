# CSmHashTable<CTpSrvKickDemote::Client,CNoLock,113>::DeleteAllObjects(void)

- ea: `0x18000ef44`
- end: `0x18000f060`
- name: `?DeleteAllObjects@?$CSmHashTable@UClient@CTpSrvKickDemote@@VCNoLock@@$0HB@@@QEAAXXZ`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000e454`

## callees

- `0x18000ef44`
- `0x18000f40c`
- `0x18001a9a8`

## pseudocode

```c
void __fastcall CSmHashTable<CTpSrvKickDemote::Client,CNoLock,113>::DeleteAllObjects(__int64 a1)
{
  int v1; // eax
  void *v3; // rcx
  _QWORD *v4; // rdi
  _QWORD *v5; // r11
  _QWORD *v6; // r8
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  _QWORD *v12; // rcx
  void *v13[2]; // [rsp+20h] [rbp-10h] BYREF

  v1 = 0;
  v3 = *(void **)(a1 + 8);
  v13[0] = 0;
  v13[1] = 0;
  if ( v3 )
  {
    v13[1] = v3;
  }
  else
  {
    v13[1] = 0;
    CSmHashTable<CTpSrvKickDemote::Client,CNoLock,113>::MoveNext(a1, v13);
    v1 = (int)v13[0];
  }
  if ( !v1 )
  {
    v4 = v13[1];
    while ( 1 )
    {
      v5 = v4;
      v6 = v4;
      v7 = 3LL * HIDWORD(v13[0]);
      if ( v4 )
        break;
LABEL_17:
      if ( !v6 )
      {
        CSmHashTable<CTpSrvKickDemote::Client,CNoLock,113>::MoveNext(a1, v13);
        v4 = v13[1];
      }
      --*(_DWORD *)(a1 + 2720);
      operator delete(v5);
      if ( LODWORD(v13[0]) )
        return;
    }
    v8 = *(_QWORD **)(a1 + 24LL * HIDWORD(v13[0]) + 8);
    v9 = *(_QWORD **)(a1 + 24LL * HIDWORD(v13[0]) + 16);
    if ( v8 == v9 )
    {
      *(_QWORD *)(a1 + 24LL * HIDWORD(v13[0]) + 16) = 0;
      *(_QWORD *)(a1 + 8 * v7 + 8) = 0;
LABEL_9:
      v4 = 0;
      v6 = 0;
LABEL_16:
      --*(_DWORD *)(a1 + 8 * v7 + 28);
      v13[1] = v4;
      goto LABEL_17;
    }
    if ( v4 == v8 )
    {
      v10 = v8[2];
      *(_QWORD *)(a1 + 24LL * HIDWORD(v13[0]) + 8) = v10;
      *(_QWORD *)(v10 + 24) = 0;
      v4 = *(_QWORD **)(a1 + 8 * v7 + 8);
    }
    else
    {
      if ( v4 == v9 )
      {
        v11 = v9[3];
        *(_QWORD *)(a1 + 24LL * HIDWORD(v13[0]) + 16) = v11;
        *(_QWORD *)(v11 + 16) = 0;
        goto LABEL_9;
      }
      v12 = v4 + 2;
      v4 = (_QWORD *)v4[2];
      *(_QWORD *)(v5[3] + 16LL) = v4;
      *(_QWORD *)(*v12 + 24LL) = v5[3];
    }
    v6 = v4;
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x18000ef44  mov     [rsp-8+arg_0], rbx
0x18000ef49  mov     [rsp-8+arg_8], rdi
0x18000ef4e  push    rbp
0x18000ef4f  mov     rbp, rsp
0x18000ef52  sub     rsp, 30h
0x18000ef56  xor     eax, eax
0x18000ef58  mov     rbx, rcx
0x18000ef5b  mov     rcx, [rcx+8]
0x18000ef5f  mov     [rbp+var_10], rax
0x18000ef63  mov     [rbp+var_10+8], rax
0x18000ef67  test    rcx, rcx
0x18000ef6a  jnz     short loc_18000EF82
0x18000ef6c  and     [rbp+var_10+8], rax
0x18000ef70  lea     rdx, [rbp+var_10]
0x18000ef74  mov     rcx, rbx
0x18000ef77  call    ?MoveNext@?$CSmHashTable@UClient@CTpSrvKickDemote@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<CTpSrvKickDemote::Client,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000ef7c  mov     rax, [rbp+var_10]
0x18000ef80  jmp     short loc_18000EF86
0x18000ef82  mov     [rbp+var_10+8], rcx
0x18000ef86  movaps  xmm0, xmmword ptr [rbp+var_10]
0x18000ef8a  movdqa  xmmword ptr [rbp+var_10], xmm0
0x18000ef8f  test    eax, eax
0x18000ef91  jnz     loc_18000F050
0x18000ef97  mov     rdi, [rbp+var_10+8]
0x18000ef9b  mov     eax, dword ptr [rbp+var_10+4]
0x18000ef9e  mov     r11, rdi
0x18000efa1  mov     r8, rdi
0x18000efa4  lea     rdx, [rax+rax*2]
0x18000efa8  test    rdi, rdi
0x18000efab  jz      short loc_18000F023
0x18000efad  mov     rcx, [rbx+rdx*8+8]
0x18000efb2  mov     rax, [rbx+rdx*8+10h]
0x18000efb7  cmp     rcx, rax
0x18000efba  jnz     short loc_18000EFCF
0x18000efbc  and     qword ptr [rbx+rdx*8+10h], 0
0x18000efc2  and     qword ptr [rbx+rdx*8+8], 0
0x18000efc8  xor     edi, edi
0x18000efca  xor     r8d, r8d
0x18000efcd  jmp     short loc_18000F01B
0x18000efcf  cmp     r11, rcx
0x18000efd2  jnz     short loc_18000EFE9
0x18000efd4  mov     rax, [rcx+10h]
0x18000efd8  mov     [rbx+rdx*8+8], rax
0x18000efdd  and     qword ptr [rax+18h], 0
0x18000efe2  mov     rdi, [rbx+rdx*8+8]
0x18000efe7  jmp     short loc_18000F018
0x18000efe9  cmp     r11, rax
0x18000efec  jnz     short loc_18000EFFE
0x18000efee  mov     rax, [rax+18h]
0x18000eff2  mov     [rbx+rdx*8+10h], rax
0x18000eff7  and     qword ptr [rax+10h], 0
0x18000effc  jmp     short loc_18000EFC8
0x18000effe  mov     rax, [r11+18h]
0x18000f002  lea     rcx, [rdi+10h]
0x18000f006  mov     rdi, [rcx]
0x18000f009  mov     [rax+10h], rdi
0x18000f00d  mov     rcx, [rcx]
0x18000f010  mov     rax, [r11+18h]
0x18000f014  mov     [rcx+18h], rax
0x18000f018  mov     r8, rdi
0x18000f01b  dec     dword ptr [rbx+rdx*8+1Ch]
0x18000f01f  mov     [rbp+var_10+8], rdi
0x18000f023  test    r8, r8
0x18000f026  jnz     short loc_18000F038
0x18000f028  lea     rdx, [rbp+var_10]
0x18000f02c  mov     rcx, rbx
0x18000f02f  call    ?MoveNext@?$CSmHashTable@UClient@CTpSrvKickDemote@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<CTpSrvKickDemote::Client,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000f034  mov     rdi, [rbp+var_10+8]
0x18000f038  dec     dword ptr [rbx+0AA0h]
0x18000f03e  mov     rcx, r11; void *
0x18000f041  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f046  cmp     dword ptr [rbp+var_10], 0
0x18000f04a  jz      loc_18000EF9B
0x18000f050  mov     rbx, [rsp+30h+arg_0]
0x18000f055  mov     rdi, [rsp+30h+arg_8]
0x18000f05a  add     rsp, 30h
0x18000f05e  pop     rbp
0x18000f05f  retn
```
