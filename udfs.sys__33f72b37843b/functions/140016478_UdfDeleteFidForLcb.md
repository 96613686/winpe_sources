# UdfDeleteFidForLcb

- ea: `0x140016478`
- end: `0x140016626`
- name: `UdfDeleteFidForLcb`
- size: `430`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14001662c`

## callees

- `0x140005e80`
- `0x14000653c`
- `0x140012308`
- `0x140016478`
- `0x140016f68`
- `0x14001758c`
- `0x14001c080`
- `0x140041110`
- `0x1400567cc`
- `0x140059090`

## pseudocode

```c
__int64 __fastcall UdfDeleteFidForLcb(__int64 a1, __int64 *a2, char a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r9
  __int64 v9; // r8
  unsigned __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  _OWORD v14[2]; // [rsp+30h] [rbp-E8h] BYREF
  __int64 v15; // [rsp+50h] [rbp-C8h]
  int v16[46]; // [rsp+60h] [rbp-B8h] BYREF

  memset(v16, 0, 0x98u);
  v15 = 0;
  UdfInitializeDirContext(v6, v16);
  memset(v14, 0, sizeof(v14));
  UdfLookupInitialDirEntry(a1, a2[3], v16, a2 + 7, 1, 0);
  if ( (*(_DWORD *)(*(_QWORD *)&v16[36] + 212LL) & 2) != 0 )
    UdfPrepareModifyIcbForScb(a1, *(_QWORD *)&v16[36], v14);
  if ( a3 )
  {
    v8 = a2[6];
    *(_DWORD *)(*(_QWORD *)&v16[8] + 20LL) ^= (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 68LL)
                                             ^ *(_DWORD *)(*(_QWORD *)&v16[8] + 20LL))
                                            & 0x3FFFFFFF;
    *(_DWORD *)(*(_QWORD *)&v16[8] + 24LL) = *(_DWORD *)(v8 + 184);
    *(_WORD *)(*(_QWORD *)&v16[8] + 28LL) = WORD2(*(_QWORD *)(v8 + 184));
    *(_BYTE *)(*(_QWORD *)&v16[8] + 18LL) &= ~4u;
    v9 = *(unsigned __int16 *)(*(_QWORD *)&v16[8] + 36LL);
    if ( *(unsigned __int8 *)(v9 + *(_QWORD *)&v16[8] + 38) == 254 )
    {
      *(_BYTE *)(v9 + *(_QWORD *)&v16[8] + 38) = 8;
    }
    else if ( *(unsigned __int8 *)(v9 + *(_QWORD *)&v16[8] + 38) == 255 )
    {
      *(_BYTE *)(v9 + *(_QWORD *)&v16[8] + 38) = 16;
    }
  }
  else
  {
    UdfMarkFidDeleted(v7, v16);
  }
  UdfSetDirtyFid(a1, v16);
  if ( (*(_DWORD *)(*(_QWORD *)&v16[36] + 212LL) & 2) != 0 )
    UdfFinishModifyIcb(a1, (__int64)v14, 1, *(__int16 **)&v16[36]);
  v10 = a2[7];
  v11 = a2[3];
  if ( v10 < *(_QWORD *)(v11 + 552) )
    *(_QWORD *)(v11 + 552) = v10;
  UdfUnpinView(a1, v14);
  return UdfCleanupDirContext(v12, v16);
}

```

## disassembly

```asm
0x140016478  mov     [rsp+arg_8], rbx
0x14001647d  mov     [rsp+arg_0], rcx
0x140016482  push    rsi
0x140016483  push    rdi
0x140016484  push    r14
0x140016486  sub     rsp, 100h
0x14001648d  mov     r14b, r8b
0x140016490  mov     rdi, rdx
0x140016493  mov     rbx, rcx
0x140016496  xor     edx, edx; Val
0x140016498  mov     r8d, 98h; Size
0x14001649e  lea     rcx, [rsp+118h+var_B8]; void *
0x1400164a3  call    memset
0x1400164a8  xorps   xmm0, xmm0
0x1400164ab  movdqu  [rsp+118h+var_D8], xmm0
0x1400164b1  mov     [rsp+118h+var_C8], 0
0x1400164ba  lea     rdx, [rsp+118h+var_B8]
0x1400164bf  call    UdfInitializeDirContext
0x1400164c4  xorps   xmm0, xmm0
0x1400164c7  movdqu  [rsp+118h+var_E8], xmm0
0x1400164cd  mov     [rsp+118h+var_F0], 0; int
0x1400164d5  mov     [rsp+118h+var_F8], 1; char
0x1400164da  lea     r9, [rdi+38h]
0x1400164de  lea     r8, [rsp+118h+var_B8]; int
0x1400164e3  mov     rdx, [rdi+18h]; int
0x1400164e7  mov     rcx, rbx; int
0x1400164ea  call    UdfLookupInitialDirEntry
0x1400164ef  mov     rdx, [rsp+118h+var_28]
0x1400164f7  mov     eax, [rdx+0D4h]
0x1400164fd  test    al, 2
0x1400164ff  jz      short loc_14001650E
0x140016501  lea     r8, [rsp+118h+var_E8]
0x140016506  mov     rcx, rbx
0x140016509  call    UdfPrepareModifyIcbForScb
0x14001650e  test    r14b, r14b
0x140016511  jnz     short loc_140016522
0x140016513  lea     rdx, [rsp+118h+var_B8]
0x140016518  call    UdfMarkFidDeleted
0x14001651d  jmp     loc_1400165B2
0x140016522  mov     r9, [rdi+30h]
0x140016526  mov     r8, [rsp+118h+var_98]
0x14001652e  mov     edx, [r8+14h]
0x140016532  mov     rax, [rbx+10h]
0x140016536  mov     ecx, edx
0x140016538  xor     ecx, [rax+44h]
0x14001653b  and     ecx, 3FFFFFFFh
0x140016541  xor     ecx, edx
0x140016543  mov     [r8+14h], ecx
0x140016547  mov     ecx, [r9+0B8h]
0x14001654e  mov     rax, [rsp+118h+var_98]
0x140016556  mov     [rax+18h], ecx
0x140016559  mov     rcx, [r9+0B8h]
0x140016560  mov     [rsp+118h+arg_18], rcx
0x140016568  shr     rcx, 20h
0x14001656c  mov     rax, [rsp+118h+var_98]
0x140016574  mov     [rax+1Ch], cx
0x140016578  mov     rax, [rsp+118h+var_98]
0x140016580  and     byte ptr [rax+12h], 0FBh
0x140016584  mov     rdx, [rsp+118h+var_98]
0x14001658c  movzx   r8d, word ptr [rdx+24h]
0x140016591  movzx   ecx, byte ptr [r8+rdx+26h]
0x140016597  sub     ecx, 0FEh
0x14001659d  jz      short loc_1400165AC
0x14001659f  cmp     ecx, 1
0x1400165a2  jnz     short loc_1400165B2
0x1400165a4  mov     byte ptr [r8+rdx+26h], 10h
0x1400165aa  jmp     short loc_1400165B2
0x1400165ac  mov     byte ptr [r8+rdx+26h], 8
0x1400165b2  lea     rdx, [rsp+118h+var_B8]
0x1400165b7  mov     rcx, rbx
0x1400165ba  call    UdfSetDirtyFid
0x1400165bf  mov     r9, [rsp+118h+var_28]
0x1400165c7  mov     eax, [r9+0D4h]
0x1400165ce  test    al, 2
0x1400165d0  jz      short loc_1400165E2
0x1400165d2  mov     r8b, 1
0x1400165d5  lea     rdx, [rsp+118h+var_E8]
0x1400165da  mov     rcx, rbx
0x1400165dd  call    UdfFinishModifyIcb
0x1400165e2  mov     rax, [rdi+38h]
0x1400165e6  mov     rcx, [rdi+18h]
0x1400165ea  cmp     rax, [rcx+228h]
0x1400165f1  jnb     short loc_1400165FA
0x1400165f3  mov     [rcx+228h], rax
0x1400165fa  lea     rdx, [rsp+118h+var_E8]
0x1400165ff  mov     rcx, rbx
0x140016602  call    UdfUnpinView
0x140016607  lea     rdx, [rsp+118h+var_B8]
0x14001660c  call    UdfCleanupDirContext
0x140016611  mov     rbx, [rsp+118h+arg_8]
0x140016619  add     rsp, 100h
0x140016620  pop     r14
0x140016622  pop     rdi
0x140016623  pop     rsi
0x140016624  retn
0x14001db98  push    rbp
0x14001db9a  sub     rsp, 30h
0x14001db9e  mov     rbp, rdx
0x14001dba1  lea     rdx, [rbp+30h]
0x14001dba5  mov     rcx, [rbp+120h]
0x14001dbac  call    UdfUnpinView
0x14001dbb1  lea     rdx, [rbp+60h]
0x14001dbb5  call    UdfCleanupDirContext
0x14001dbba  nop
0x14001dbbb  add     rsp, 30h
0x14001dbbf  pop     rbp
0x14001dbc0  retn
```
