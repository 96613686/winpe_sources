# RtlpHpLfhBucketUpdateAffinityMapping

- ea: `0x1400cdf4c`
- end: `0x1400ce2bb`
- name: `RtlpHpLfhBucketUpdateAffinityMapping`
- size: `879`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000f0f0`
- `0x14000ffec`
- `0x140013c44`
- `0x1400c7b18`

## callees

- `0x1400b5904`
- `0x1400c7588`
- `0x1400c75b8`
- `0x1400cddc8`
- `0x1400cdf4c`
- `0x1400ce94c`
- `0x1400d0578`
- `0x1400f3620`

## pseudocode

```c
unsigned __int64 __fastcall RtlpHpLfhBucketUpdateAffinityMapping(__int64 a1, unsigned __int8 *a2)
{
  __int64 v4; // rdx
  char CurrentProcessorNumber; // di
  __int64 v6; // r8
  unsigned int v7; // esi
  unsigned int v8; // eax
  unsigned int v9; // edi
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // r10
  unsigned __int64 result; // rax
  __int16 v15; // r9
  struct _EXCEPTION_REGISTRATION_RECORD *v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // r15
  volatile signed __int8 *v19; // rdi
  struct _EXCEPTION_REGISTRATION_RECORD *ExceptionList; // rdx
  __int64 v21; // rcx
  unsigned int SlotInfo; // eax
  __int64 v23; // r13
  char v24; // r8
  unsigned __int8 *v25; // r12
  __int64 v26; // rax
  unsigned __int64 v27; // rax
  struct _EXCEPTION_REGISTRATION_RECORD *v28; // rdx
  __int64 v29; // rcx
  unsigned __int16 v30; // [rsp+30h] [rbp-178h]
  unsigned int v32; // [rsp+40h] [rbp-168h]
  __int64 updated; // [rsp+40h] [rbp-168h]
  unsigned __int64 v34; // [rsp+48h] [rbp-160h]
  _BYTE v35[256]; // [rsp+60h] [rbp-148h] BYREF

  v32 = *a2 >> 1;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v7 = 1;
  v8 = *(unsigned __int8 *)(a1 + 64);
  v9 = CurrentProcessorNumber & 0x3F;
  if ( v9 >= v8 )
  {
    if ( v9 == v8 || (_BYTE)v8 == 1 )
      v9 = 0;
    else
      v9 = *(unsigned __int8 *)(v9 - v8 - 1 + *(_QWORD *)(a1 + 56));
  }
  v10 = *((_QWORD *)&KeGetPcr()->NtTib.ExceptionList[182].Handler + (unsigned int)(*(_DWORD *)(a1 + 76) - 1));
  if ( !v10 )
    v10 = RtlpHpLfhThreadDataInitializeSet(a1, v4, v6);
  v11 = a1 + ((unsigned __int64)(unsigned __int16)v10 << 6);
  v12 = (unsigned __int64)v9 << 8;
  v13 = v12 + a1 + 1472;
  v34 = HIDWORD(v10);
  if ( v11 < a1 + ((unsigned __int64)*(unsigned __int8 *)(a1 + 64) << 8) + 1472 )
  {
    v18 = 0;
    if ( v11 != v13 )
    {
      ExceptionList = KeGetPcr()->NtTib.ExceptionList;
      v21 = (unsigned int)(*(_DWORD *)(a1 + 76) - 1);
      result = (v12 + 1472) >> 6;
      *((_WORD *)&ExceptionList[182].Handler + 4 * v21) = result;
      *((_WORD *)&ExceptionList[182].Handler + 4 * v21 + 1) = WORD1(v10);
      *((_BYTE *)&ExceptionList[182].Handler + 8 * v21 + 4) = v9;
      *((_BYTE *)&ExceptionList[182].Handler + 8 * v21 + 5) = BYTE5(v10);
      *((_WORD *)&ExceptionList[182].Handler + 4 * v21 + 3) = HIWORD(v10);
      return result;
    }
  }
  else
  {
    result = *(unsigned __int16 *)(v11 + 2LL * v32);
    v15 = *(_WORD *)(v13 + 2LL * v32);
    v30 = *(_WORD *)(v11 + 2LL * v32);
    if ( BYTE4(v10) != (_BYTE)v9 )
    {
      v16 = KeGetPcr()->NtTib.ExceptionList;
      v17 = *(_DWORD *)(a1 + 76) - 1;
      LOBYTE(v34) = v9;
      *((_DWORD *)&v16[182].Handler + 2 * v17) = v10;
      *((_BYTE *)&v16[182].Handler + 8 * v17 + 4) = v9;
      *((_BYTE *)&v16[182].Handler + 8 * v17 + 5) = BYTE5(v10);
      *((_WORD *)&v16[182].Handler + 4 * v17 + 3) = HIWORD(v10);
      result = v30;
    }
    if ( (_WORD)result != v15 )
    {
      *(_WORD *)(v11 + 2LL * v32) = v15;
      return result;
    }
    v18 = a1 + ((unsigned __int64)(unsigned __int16)v10 << 6);
    v11 = v12 + a1 + 1472;
  }
  v19 = (volatile signed __int8 *)(a2 + 104);
  result = (unsigned __int8)_InterlockedCompareExchange8(v19, 1, 0);
  if ( !(_BYTE)result )
  {
    SlotInfo = RtlpHpLfhBucketGetSlotInfo(a1, a2, v35);
    v23 = v32;
    v24 = 0;
    if ( BYTE5(v10) >= SlotInfo - 1 )
      v24 = SlotInfo < *(unsigned __int8 *)(a1 + 64);
    updated = RtlpHpAffinityMgrUpdateProcess(
                (_DWORD)v19,
                *(unsigned __int16 *)(v11 + 2LL * v32),
                (unsigned int)v35,
                SlotInfo,
                v24);
    if ( (_DWORD)updated )
    {
      if ( (_DWORD)updated == 1 )
      {
        *(_WORD *)(v11 + 2 * v23) = WORD2(updated);
        if ( v18 )
          *(_WORD *)(v18 + 2 * v23) = WORD2(updated);
        v28 = KeGetPcr()->NtTib.ExceptionList;
        v29 = (unsigned int)(*(_DWORD *)(a1 + 76) - 1);
        *((_DWORD *)&v28[182].Handler + 2 * v29) = v10;
        *((_BYTE *)&v28[182].Handler + 8 * v29 + 4) = v34;
        *((_BYTE *)&v28[182].Handler + 8 * v29 + 5) = BYTE5(v10) + 1;
        v25 = a2;
        goto LABEL_34;
      }
      if ( (_DWORD)updated != 2 )
      {
        v25 = a2;
        if ( (_DWORD)updated != 3 || (v26 = RtlpHpLfhContextSlotAllocate(a1, a2)) == 0 )
        {
          v7 = 0;
          return RtlpHpAffinityMgrUpdateComplete(v25 + 104, (unsigned int)updated, v7);
        }
        ++a2[1];
        v27 = (unsigned __int64)(v26 - a1) >> 6;
        *(_WORD *)(v11 + 2 * v23) = v27;
        if ( v18 )
          *(_WORD *)(v18 + 2 * v23) = v27;
        if ( (RtlpHpLfhPerfFlags & 0x40) == 0 )
          return RtlpHpAffinityMgrUpdateComplete(v25 + 104, (unsigned int)updated, v7);
        v28 = KeGetPcr()->NtTib.ExceptionList;
        v29 = (unsigned int)(*(_DWORD *)(a1 + 76) - 1);
        *((_DWORD *)&v28[182].Handler + 2 * v29) = v10;
        *((_WORD *)&v28[182].Handler + 4 * v29 + 2) = (unsigned __int8)v34;
LABEL_34:
        *((_WORD *)&v28[182].Handler + 4 * v29 + 3) = HIWORD(v10);
        return RtlpHpAffinityMgrUpdateComplete(v25 + 104, (unsigned int)updated, v7);
      }
    }
    v25 = a2;
    return RtlpHpAffinityMgrUpdateComplete(v25 + 104, (unsigned int)updated, v7);
  }
  return result;
}

```

## disassembly

```asm
0x1400cdf4c  mov     [rsp+arg_10], rbx
0x1400cdf51  push    rbp
0x1400cdf52  push    rsi
0x1400cdf53  push    rdi
0x1400cdf54  push    r12
0x1400cdf56  push    r13
0x1400cdf58  push    r14
0x1400cdf5a  push    r15
0x1400cdf5c  sub     rsp, 170h
0x1400cdf63  mov     rax, cs:__security_cookie
0x1400cdf6a  xor     rax, rsp
0x1400cdf6d  mov     [rsp+1A8h+var_48], rax
0x1400cdf75  movzx   eax, byte ptr [rdx]
0x1400cdf78  mov     rbp, rcx
0x1400cdf7b  shr     eax, 1
0x1400cdf7d  xor     ecx, ecx; ProcNumber
0x1400cdf7f  mov     dword ptr [rsp+1A8h+var_168], eax
0x1400cdf83  mov     r13, rdx
0x1400cdf86  mov     [rsp+1A8h+var_170], rdx
0x1400cdf8b  call    KeGetCurrentProcessorNumberEx
0x1400cdf90  mov     edi, eax
0x1400cdf92  mov     esi, 1
0x1400cdf97  movzx   eax, byte ptr [rbp+40h]
0x1400cdf9b  and     edi, 3Fh
0x1400cdf9e  cmp     edi, eax
0x1400cdfa0  jb      short loc_1400CDFB9
0x1400cdfa2  jz      short loc_1400CDFB7
0x1400cdfa4  cmp     al, sil
0x1400cdfa7  jz      short loc_1400CDFB7
0x1400cdfa9  sub     edi, eax
0x1400cdfab  mov     rax, [rbp+38h]
0x1400cdfaf  sub     edi, esi
0x1400cdfb1  movzx   edi, byte ptr [rdi+rax]
0x1400cdfb5  jmp     short loc_1400CDFB9
0x1400cdfb7  xor     edi, edi
0x1400cdfb9  mov     rcx, gs:0
0x1400cdfc2  mov     eax, [rbp+4Ch]
0x1400cdfc5  sub     eax, esi
0x1400cdfc7  mov     rbx, [rcx+rax*8+0B68h]
0x1400cdfcf  test    rbx, rbx
0x1400cdfd2  jz      short loc_1400CDFDB
0x1400cdfd4  mov     [rsp+1A8h+var_150], rbx
0x1400cdfd9  jmp     short loc_1400CDFE6
0x1400cdfdb  mov     rcx, rbp
0x1400cdfde  call    RtlpHpLfhThreadDataInitializeSet
0x1400cdfe3  mov     rbx, rax
0x1400cdfe6  movzx   eax, byte ptr [rbp+40h]
0x1400cdfea  lea     r10, [rbp+5C0h]
0x1400cdff1  shl     rax, 8
0x1400cdff5  mov     r11, rbx
0x1400cdff8  add     rax, 5C0h
0x1400cdffe  shr     r11, 10h
0x1400ce002  movzx   r14d, bx
0x1400ce006  mov     r15, rbx
0x1400ce009  shl     r14, 6
0x1400ce00d  mov     r12, rbx
0x1400ce010  shr     r15, 20h
0x1400ce014  mov     r9, rbx
0x1400ce017  shr     r9, 30h
0x1400ce01b  add     rax, rbp
0x1400ce01e  mov     r8d, edi
0x1400ce021  add     r14, rbp
0x1400ce024  shl     r8, 8
0x1400ce028  shr     r12, 28h
0x1400ce02c  add     r10, r8
0x1400ce02f  mov     [rsp+1A8h+var_150], r11
0x1400ce034  mov     [rsp+1A8h+var_160], r15
0x1400ce039  mov     [rsp+1A8h+var_158], r9
0x1400ce03e  cmp     r14, rax
0x1400ce041  jb      short loc_1400CE0C2
0x1400ce043  mov     r8d, dword ptr [rsp+1A8h+var_168]
0x1400ce048  movzx   eax, word ptr [r14+r8*2]
0x1400ce04d  movzx   r9d, word ptr [r10+r8*2]
0x1400ce052  mov     [rsp+1A8h+var_178], ax
0x1400ce057  cmp     r15b, dil
0x1400ce05a  jz      short loc_1400CE0A4
0x1400ce05c  mov     rdx, gs:0
0x1400ce065  mov     eax, [rbp+4Ch]
0x1400ce068  sub     eax, esi
0x1400ce06a  mov     byte ptr [rsp+1A8h+var_160], dil
0x1400ce06f  mov     ecx, eax
0x1400ce071  mov     [rdx+rax*8+0B68h], bx
0x1400ce079  mov     [rdx+rax*8+0B6Ah], r11w
0x1400ce082  mov     [rdx+rax*8+0B6Ch], dil
0x1400ce08a  mov     [rdx+rax*8+0B6Dh], r12b
0x1400ce092  mov     rax, [rsp+1A8h+var_158]
0x1400ce097  mov     [rdx+rcx*8+0B6Eh], ax
0x1400ce09f  movzx   eax, [rsp+1A8h+var_178]
0x1400ce0a4  cmp     ax, r9w
0x1400ce0a8  jz      short loc_1400CE0B4
0x1400ce0aa  mov     [r14+r8*2], r9w
0x1400ce0af  jmp     loc_1400CE28F
0x1400ce0b4  mov     r15, r14
0x1400ce0b7  mov     r14, r10
0x1400ce0ba  xor     ecx, ecx
0x1400ce0bc  lea     rdi, [r13+68h]
0x1400ce0c0  jmp     short loc_1400CE11E
0x1400ce0c2  xor     r15d, r15d
0x1400ce0c5  cmp     r14, r10
0x1400ce0c8  jz      short loc_1400CE0BA
0x1400ce0ca  mov     rdx, gs:0
0x1400ce0d3  lea     rax, [r8+5C0h]
0x1400ce0da  mov     ecx, [rbp+4Ch]
0x1400ce0dd  sub     ecx, esi
0x1400ce0df  shr     rax, 6
0x1400ce0e3  mov     [rdx+rcx*8+0B68h], ax
0x1400ce0eb  mov     [rdx+rcx*8+0B6Ah], r11w
0x1400ce0f4  mov     [rdx+rcx*8+0B6Ch], dil
0x1400ce0fc  mov     [rdx+rcx*8+0B6Dh], r12b
0x1400ce104  mov     [rdx+rcx*8+0B6Eh], r9w
0x1400ce10d  jmp     loc_1400CE28F
0x1400ce112  test    ecx, ecx
0x1400ce114  jz      loc_1400CE28F
0x1400ce11a  pause
0x1400ce11c  dec     ecx
0x1400ce11e  xor     eax, eax
0x1400ce120  lock cmpxchg [rdi], sil
0x1400ce125  jnz     short loc_1400CE112
0x1400ce127  lea     r8, [rsp+1A8h+var_148]
0x1400ce12c  mov     rdx, r13
0x1400ce12f  mov     rcx, rbp
0x1400ce132  call    RtlpHpLfhBucketGetSlotInfo
0x1400ce137  mov     r13d, dword ptr [rsp+1A8h+var_168]
0x1400ce13c  xor     r8d, r8d
0x1400ce13f  movzx   ecx, r12b
0x1400ce143  lea     edx, [rax-1]
0x1400ce146  movzx   r9d, word ptr [r14+r13*2]
0x1400ce14b  cmp     ecx, edx
0x1400ce14d  jb      short loc_1400CE159
0x1400ce14f  movzx   ecx, byte ptr [rbp+40h]
0x1400ce153  cmp     eax, ecx
0x1400ce155  cmovb   r8d, esi
0x1400ce159  mov     edx, r9d
0x1400ce15c  mov     [rsp+1A8h+var_188], r8d
0x1400ce161  mov     r9d, eax
0x1400ce164  lea     r8, [rsp+1A8h+var_148]
0x1400ce169  mov     rcx, rdi
0x1400ce16c  call    RtlpHpAffinityMgrUpdateProcess
0x1400ce171  mov     [rsp+1A8h+var_168], rax
0x1400ce176  mov     rdi, rax
0x1400ce179  mov     ecx, eax
0x1400ce17b  test    eax, eax
0x1400ce17d  jz      loc_1400CE27B
0x1400ce183  sub     ecx, esi
0x1400ce185  jz      loc_1400CE217
0x1400ce18b  sub     ecx, esi
0x1400ce18d  jz      loc_1400CE27B
0x1400ce193  mov     r12, [rsp+1A8h+var_170]
0x1400ce198  cmp     ecx, esi
0x1400ce19a  jnz     short loc_1400CE1AC
0x1400ce19c  mov     rdx, r12
0x1400ce19f  mov     rcx, rbp
0x1400ce1a2  call    RtlpHpLfhContextSlotAllocate
0x1400ce1a7  test    rax, rax
0x1400ce1aa  jnz     short loc_1400CE1B3
0x1400ce1ac  xor     esi, esi
0x1400ce1ae  jmp     loc_1400CE280
0x1400ce1b3  add     [r12+1], sil
0x1400ce1b8  sub     rax, rbp
0x1400ce1bb  shr     rax, 6
0x1400ce1bf  mov     [r14+r13*2], ax
0x1400ce1c4  test    r15, r15
0x1400ce1c7  jz      short loc_1400CE1CE
0x1400ce1c9  mov     [r15+r13*2], ax
0x1400ce1ce  mov     eax, cs:RtlpHpLfhPerfFlags
0x1400ce1d4  test    al, 40h
0x1400ce1d6  jz      loc_1400CE280
0x1400ce1dc  mov     rdx, gs:0
0x1400ce1e5  mov     eax, [rbp+4Ch]
0x1400ce1e8  sub     eax, esi
0x1400ce1ea  mov     ecx, eax
0x1400ce1ec  mov     [rdx+rax*8+0B68h], bx
0x1400ce1f4  mov     rax, [rsp+1A8h+var_150]
0x1400ce1f9  mov     [rdx+rcx*8+0B6Ah], ax
0x1400ce201  mov     rax, [rsp+1A8h+var_160]
0x1400ce206  mov     [rdx+rcx*8+0B6Ch], al
0x1400ce20d  mov     byte ptr [rdx+rcx*8+0B6Dh], 0
0x1400ce215  jmp     short loc_1400CE26C
0x1400ce217  movzx   eax, word ptr [rsp+1A8h+var_168+4]
0x1400ce21c  mov     [r14+r13*2], ax
0x1400ce221  test    r15, r15
0x1400ce224  jz      short loc_1400CE22B
0x1400ce226  mov     [r15+r13*2], ax
0x1400ce22b  mov     rdx, gs:0
0x1400ce234  mov     eax, [rbp+4Ch]
0x1400ce237  sub     eax, esi
0x1400ce239  mov     ecx, eax
0x1400ce23b  add     r12b, sil
0x1400ce23e  mov     [rdx+rax*8+0B68h], bx
0x1400ce246  mov     rax, [rsp+1A8h+var_150]
0x1400ce24b  mov     [rdx+rcx*8+0B6Ah], ax
0x1400ce253  mov     rax, [rsp+1A8h+var_160]
0x1400ce258  mov     [rdx+rcx*8+0B6Ch], al
0x1400ce25f  mov     [rdx+rcx*8+0B6Dh], r12b
0x1400ce267  mov     r12, [rsp+1A8h+var_170]
0x1400ce26c  mov     rax, [rsp+1A8h+var_158]
0x1400ce271  mov     [rdx+rcx*8+0B6Eh], ax
0x1400ce279  jmp     short loc_1400CE280
0x1400ce27b  mov     r12, [rsp+1A8h+var_170]
0x1400ce280  mov     r8d, esi
0x1400ce283  lea     rcx, [r12+68h]
0x1400ce288  mov     edx, edi
0x1400ce28a  call    RtlpHpAffinityMgrUpdateComplete
0x1400ce28f  mov     rcx, [rsp+1A8h+var_48]
0x1400ce297  xor     rcx, rsp; StackCookie
0x1400ce29a  call    __security_check_cookie
0x1400ce29f  mov     rbx, [rsp+1A8h+arg_10]
0x1400ce2a7  add     rsp, 170h
0x1400ce2ae  pop     r15
0x1400ce2b0  pop     r14
0x1400ce2b2  pop     r13
0x1400ce2b4  pop     r12
0x1400ce2b6  pop     rdi
0x1400ce2b7  pop     rsi
0x1400ce2b8  pop     rbp
0x1400ce2b9  retn
```
