# SkpgVerifyExtensionTableExtent

- ea: `0x1400a6604`
- end: `0x1400a6826`
- name: `SkpgVerifyExtensionTableExtent`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400a682c`

## callees

- `0x1400202b0`
- `0x1400202ec`
- `0x14002c428`
- `0x140032c68`
- `0x1400a5264`
- `0x1400a5694`
- `0x1400a6604`
- `0x1400a7148`

## pseudocode

```c
unsigned int *__fastcall SkpgVerifyExtensionTableExtent(__int64 a1, __int64 a2)
{
  unsigned int *result; // rax
  int v5; // ebp
  __int64 v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // rcx
  _DWORD **v9; // rax
  _DWORD *v10; // r13
  _DWORD *v11; // r15
  _DWORD *v12; // rsi
  unsigned __int16 v13; // ax
  unsigned int v14; // r14d
  __int64 v15; // rbp
  __int64 v16; // r10
  int v17; // eax
  int v18; // [rsp+88h] [rbp+10h]

  result = **(unsigned int ***)(a2 + 24);
  if ( result )
  {
    if ( *(_DWORD *)(a1 + 52) || (result = (unsigned int *)*result, (_DWORD)result) )
    {
      v5 = *(_DWORD *)(a1 + 52);
      v6 = *(unsigned int *)(a1 + 752);
      v18 = *(_DWORD *)(a1 + 48);
      *(_DWORD *)(a1 + 48) = *(_DWORD *)(a1 + 744);
      *(_DWORD *)(a1 + 52) = *(_DWORD *)(a1 + 748);
      SkAcquireSpinLockSharedAtDpcLevel(&SkpgExtensionTableLock);
      v9 = *(_DWORD ***)(a2 + 24);
      v10 = *v9;
      if ( (unsigned int)v6 < **v9 )
      {
        _mm_lfence();
        v11 = *(_DWORD **)&v10[2 * v6 + 2];
        v8 = *(unsigned int *)(a1 + 48);
        if ( (unsigned int)v8 < *v11 )
        {
          v12 = &v11[12 * v8];
          do
          {
            while ( (SkmiAssertionTimestamp & 1) != 0 )
              _mm_pause();
            v13 = SkpgExtentCrc(a1, v12 + 6);
            v14 = *((unsigned __int8 *)v12 + 27);
            v15 = v13;
          }
          while ( !(unsigned int)SkpgReleaseAssertionTimestamp(a1, v16) );
          if ( (_DWORD)v15 == v14 )
          {
            SkpgLogEvent(
              a1,
              45,
              *((unsigned __int16 *)v12 + 12),
              v6,
              *(unsigned int *)(a1 + 48),
              *(unsigned int *)(a1 + 52));
            if ( *((_WORD *)v12 + 12) == 4098 || *((_WORD *)v12 + 12) == 4118 )
              SkpgVerifyMemoryExtent(a1, v12 + 6);
            v17 = *(_DWORD *)(a1 + 48);
            v8 = (unsigned int)(v17 + 1);
            *(_DWORD *)(a1 + 48) = v8;
            if ( *(_DWORD *)(a1 + 52) )
              *(_DWORD *)(a1 + 48) = v17;
            else
              ++v17;
            if ( v17 != *v11 )
              goto LABEL_29;
          }
          else
          {
            SkpgBugCheck(a1, 0, v15, 4356, v15 ^ v14);
          }
          LODWORD(v6) = v6 + 1;
        }
        else
        {
          if ( (*(_DWORD *)(a2 + 32) & 1) == 0 && ((_DWORD)v8 || *(_DWORD *)(a1 + 52)) )
            SkpgBugCheck(a1, a2, 0, 0, *(unsigned int *)(a1 + 48));
          LODWORD(v6) = v6 + 1;
        }
        *(_QWORD *)(a1 + 48) = 0;
        *(_QWORD *)(a1 + 56) = 0;
      }
      else if ( (*(_DWORD *)(a2 + 32) & 1) == 0 && v5 )
      {
        SkpgBugCheck(a1, a2, 0, 0, -1);
      }
LABEL_29:
      _InterlockedDecrement(&SkpgExtensionTableLock);
      SkTrackSpinLockRelease(v8, v7);
      *(_DWORD *)(a1 + 744) = *(_DWORD *)(a1 + 48);
      *(_DWORD *)(a1 + 48) = v18;
      result = (unsigned int *)*(unsigned int *)(a1 + 52);
      *(_DWORD *)(a1 + 748) = (_DWORD)result;
      *(_DWORD *)(a1 + 752) = v6;
      if ( (unsigned int)v6 >= *v10 )
      {
        *(_DWORD *)(a1 + 52) = 0;
        *(_QWORD *)(a1 + 744) = 0;
        *(_DWORD *)(a1 + 752) = 0;
        *(_QWORD *)(a1 + 56) = 0;
      }
      else
      {
        *(_DWORD *)(a1 + 52) = 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400a6604  push    rbx
0x1400a6606  push    rbp
0x1400a6607  push    rsi
0x1400a6608  push    rdi
0x1400a6609  push    r12
0x1400a660b  push    r13
0x1400a660d  push    r14
0x1400a660f  push    r15
0x1400a6611  sub     rsp, 38h
0x1400a6615  mov     rax, [rdx+18h]
0x1400a6619  xor     r14d, r14d
0x1400a661c  mov     rsi, rdx
0x1400a661f  mov     rbx, rcx
0x1400a6622  mov     rax, [rax]
0x1400a6625  test    rax, rax
0x1400a6628  jz      loc_1400A6814
0x1400a662e  cmp     [rcx+34h], r14d
0x1400a6632  jnz     short loc_1400A663E
0x1400a6634  mov     eax, [rax]
0x1400a6636  test    eax, eax
0x1400a6638  jz      loc_1400A6814
0x1400a663e  mov     eax, [rcx+30h]
0x1400a6641  mov     ebp, [rcx+34h]
0x1400a6644  mov     edi, [rcx+2F0h]
0x1400a664a  mov     [rsp+78h+arg_8], eax
0x1400a6651  mov     eax, [rcx+2E8h]
0x1400a6657  mov     [rcx+30h], eax
0x1400a665a  mov     eax, [rcx+2ECh]
0x1400a6660  mov     [rcx+34h], eax
0x1400a6663  lea     rcx, SkpgExtensionTableLock
0x1400a666a  call    SkAcquireSpinLockSharedAtDpcLevel
0x1400a666f  mov     rax, [rsi+18h]
0x1400a6673  mov     r13, [rax]
0x1400a6676  cmp     edi, [r13+0]
0x1400a667a  jb      short loc_1400A66AE
0x1400a667c  mov     eax, [rsi+20h]
0x1400a667f  test    al, 1
0x1400a6681  jnz     loc_1400A67BD
0x1400a6687  test    ebp, ebp
0x1400a6689  jz      loc_1400A67BD
0x1400a668f  xor     r9d, r9d
0x1400a6692  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFFh
0x1400a669b  xor     r8d, r8d
0x1400a669e  mov     rdx, rsi
0x1400a66a1  mov     rcx, rbx
0x1400a66a4  call    SkpgBugCheck
0x1400a66a9  jmp     loc_1400A67BD
0x1400a66ae  lfence
0x1400a66b1  mov     r15, [r13+rdi*8+8]
0x1400a66b6  mov     ecx, [rbx+30h]
0x1400a66b9  cmp     ecx, [r15]
0x1400a66bc  jb      short loc_1400A66EC
0x1400a66be  mov     eax, [rsi+20h]
0x1400a66c1  test    al, 1
0x1400a66c3  jnz     short loc_1400A66E5
0x1400a66c5  test    ecx, ecx
0x1400a66c7  jnz     short loc_1400A66CF
0x1400a66c9  cmp     [rbx+34h], r14d
0x1400a66cd  jz      short loc_1400A66E5
0x1400a66cf  mov     [rsp+78h+var_58], rcx
0x1400a66d4  xor     r9d, r9d
0x1400a66d7  mov     rcx, rbx
0x1400a66da  xor     r8d, r8d
0x1400a66dd  mov     rdx, rsi
0x1400a66e0  call    SkpgBugCheck
0x1400a66e5  inc     edi
0x1400a66e7  jmp     loc_1400A67B5
0x1400a66ec  lea     rsi, [rcx+rcx*2]
0x1400a66f0  shl     rsi, 4
0x1400a66f4  add     rsi, r15
0x1400a66f7  jmp     short loc_1400A66FB
0x1400a66f9  pause
0x1400a66fb  mov     r10, cs:SkmiAssertionTimestamp
0x1400a6702  test    r10b, 1
0x1400a6706  jnz     short loc_1400A66F9
0x1400a6708  lea     rdx, [rsi+18h]
0x1400a670c  mov     rcx, rbx
0x1400a670f  call    SkpgExtentCrc
0x1400a6714  movzx   r14d, byte ptr [rsi+1Bh]
0x1400a6719  mov     rdx, r10
0x1400a671c  mov     rcx, rbx
0x1400a671f  movzx   ebp, ax
0x1400a6722  call    SkpgReleaseAssertionTimestamp
0x1400a6727  test    eax, eax
0x1400a6729  jz      short loc_1400A66FB
0x1400a672b  cmp     ebp, r14d
0x1400a672e  jz      short loc_1400A6753
0x1400a6730  mov     eax, r14d
0x1400a6733  mov     r8d, ebp
0x1400a6736  xor     rax, rbp
0x1400a6739  xor     edx, edx
0x1400a673b  mov     r9d, 1104h
0x1400a6741  mov     [rsp+78h+var_58], rax
0x1400a6746  mov     rcx, rbx
0x1400a6749  call    SkpgBugCheck
0x1400a674e  xor     r14d, r14d
0x1400a6751  jmp     short loc_1400A67B3
0x1400a6753  movzx   r8d, word ptr [rsi+18h]
0x1400a6758  mov     r9, rdi
0x1400a675b  mov     ecx, [rbx+34h]
0x1400a675e  mov     edx, [rbx+30h]
0x1400a6761  mov     [rsp+78h+var_50], rcx
0x1400a6766  mov     rcx, rbx
0x1400a6769  mov     [rsp+78h+var_58], rdx
0x1400a676e  mov     edx, 2Dh ; '-'
0x1400a6773  call    SkpgLogEvent
0x1400a6778  movzx   ecx, word ptr [rsi+18h]
0x1400a677c  sub     ecx, 1002h
0x1400a6782  jz      short loc_1400A6789
0x1400a6784  cmp     ecx, 14h
0x1400a6787  jnz     short loc_1400A6795
0x1400a6789  lea     rdx, [rsi+18h]
0x1400a678d  mov     rcx, rbx
0x1400a6790  call    SkpgVerifyMemoryExtent
0x1400a6795  mov     eax, [rbx+30h]
0x1400a6798  xor     r14d, r14d
0x1400a679b  lea     ecx, [rax+1]
0x1400a679e  mov     [rbx+30h], ecx
0x1400a67a1  cmp     [rbx+34h], r14d
0x1400a67a5  jz      short loc_1400A67AC
0x1400a67a7  mov     [rbx+30h], eax
0x1400a67aa  jmp     short loc_1400A67AE
0x1400a67ac  mov     eax, ecx
0x1400a67ae  cmp     eax, [r15]
0x1400a67b1  jnz     short loc_1400A67BD
0x1400a67b3  inc     edi
0x1400a67b5  mov     [rbx+30h], r14
0x1400a67b9  mov     [rbx+38h], r14
0x1400a67bd  lock dec cs:SkpgExtensionTableLock
0x1400a67c4  call    SkTrackSpinLockRelease
0x1400a67c9  mov     eax, [rbx+30h]
0x1400a67cc  mov     [rbx+2E8h], eax
0x1400a67d2  mov     eax, [rsp+78h+arg_8]
0x1400a67d9  mov     [rbx+30h], eax
0x1400a67dc  mov     eax, [rbx+34h]
0x1400a67df  mov     [rbx+2ECh], eax
0x1400a67e5  mov     [rbx+2F0h], edi
0x1400a67eb  cmp     edi, [r13+0]
0x1400a67ef  jnb     short loc_1400A67FA
0x1400a67f1  mov     dword ptr [rbx+34h], 1
0x1400a67f8  jmp     short loc_1400A6814
0x1400a67fa  mov     [rbx+34h], r14d
0x1400a67fe  mov     qword ptr [rbx+2E8h], 0
0x1400a6809  mov     [rbx+2F0h], r14d
0x1400a6810  mov     [rbx+38h], r14
0x1400a6814  add     rsp, 38h
0x1400a6818  pop     r15
0x1400a681a  pop     r14
0x1400a681c  pop     r13
0x1400a681e  pop     r12
0x1400a6820  pop     rdi
0x1400a6821  pop     rsi
0x1400a6822  pop     rbp
0x1400a6823  pop     rbx
0x1400a6824  retn
```
