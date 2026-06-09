# SkmmCreateEnclave

- ea: `0x14006b310`
- end: `0x14006b665`
- name: `SkmmCreateEnclave`
- size: `853`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, __int64, __int64, __int64, ULONG_PTR, char, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140014dd0`

## callees

- `0x140001320`
- `0x140002ef0`
- `0x14000f0f0`
- `0x140012750`
- `0x14001e518`
- `0x140034154`
- `0x140034dec`
- `0x140037e68`
- `0x140050634`
- `0x14005b200`
- `0x14006b310`
- `0x140070cd8`
- `0x1400809dc`
- `0x140099724`
- `0x1400a0df8`
- `0x1400a18a0`
- `0x1400a1950`
- `0x1400ae4a8`
- `0x1400b040c`
- `0x1400c1eec`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmmCreateEnclave(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        ULONG_PTR a6,
        char a7,
        __int64 a8)
{
  int v9; // r12d
  ULONG_PTR v11; // r14
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rax
  __int64 result; // rax
  __int64 v15; // r15
  int ProcessAddressSpace; // ebx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  _QWORD *v20; // rdi
  int LockedVad; // eax
  __int64 v22; // rsi
  __int64 v23; // r8
  BCRYPT_ALG_HANDLE *Pool; // rax
  __int64 v25; // rdx
  ULONG_PTR v26; // [rsp+30h] [rbp-28h] BYREF
  __int64 v27; // [rsp+38h] [rbp-20h] BYREF
  void *v28; // [rsp+40h] [rbp-18h] BYREF
  __int64 v29; // [rsp+48h] [rbp-10h] BYREF

  v9 = a3;
  v27 = 0;
  v26 = 0;
  v11 = 0;
  v28 = 0;
  v29 = 0;
  if ( !SkpspEnclaveInfo || a7 )
    return 3221225659LL;
  v12 = a2 >> 12;
  if ( (a2 & 0xFFF) == 0 && (v12 & 0x1FF) == 0 && (a3 & 0xFFF) == 0 )
  {
    v13 = (a2 + a3 - 1) >> 12;
    if ( v13 >= v12 && (((_WORD)v13 + 1) & 0x1FF) == 0 )
    {
      result = SkpsReferenceProcessByHandle(a1, 1, &v27, 511);
      if ( (int)result < 0 )
        return result;
      v15 = v27;
      ProcessAddressSpace = SkmiConfigureEnclavePartition(*(_QWORD *)(v27 + 72));
      if ( ProcessAddressSpace < 0 )
        goto LABEL_32;
      if ( a5 )
      {
        v17 = SkmmMapDataTransfer(a5, a6, 1u, &v26, 0);
        v11 = v26;
        ProcessAddressSpace = v17;
        if ( v17 < 0 )
        {
LABEL_30:
          if ( v11 )
            SkmmUnmapDataTransfer(v11);
LABEL_32:
          SkReleaseRundownProtection(v15 + 80, 0);
          return (unsigned int)ProcessAddressSpace;
        }
      }
      v18 = SkobCreateObjectEx(0, &SkmiEnclaveType, 0, &v28);
      v20 = v28;
      ProcessAddressSpace = v18;
      if ( v18 < 0 )
        goto LABEL_26;
      memset_0(v28, 0, 0x2C0u);
      v20[78] = v15;
      SkobReferenceObject(v15);
      LockedVad = SkmiCreateLockedVad(a2, v9, (int)v20 + 536, 0, (__int64)&v29);
      v22 = v29;
      ProcessAddressSpace = LockedVad;
      v19 = 0x800000000000LL;
      if ( LockedVad >= 0 )
      {
        *(_QWORD *)(v29 + 48) = *(_QWORD *)(v29 + 48) & 0xFF838FFFFFFFFFFFuLL | 0x10400000000000LL;
        v20[80] = 0;
        v20[85] = 0;
        v20[77] = v20 + 76;
        v20[76] = v20 + 76;
        v20[30] = a4;
        *(_QWORD *)(v22 + 48) |= 0x800000000000uLL;
        *((_DWORD *)v20 + 1) = 0;
        v20[3] = v20 + 2;
        v20[2] = v20 + 2;
        v20[5] = v20 + 4;
        v20[4] = v20 + 4;
        v23 = *(_QWORD *)(v15 + 72);
        if ( v23 )
          v23 = *(_QWORD *)(v23 + 24);
        ProcessAddressSpace = SkmmCreateProcessAddressSpace(v20, v15, v23);
        if ( ProcessAddressSpace >= 0 )
        {
          SkobReferenceObject(v20);
          v20[10] = 1;
          *(_DWORD *)v20 |= 0x203u;
          v20[6] = *(_QWORD *)(v15 + 48);
          *(_QWORD *)(v22 + 48) &= ~0x800000000000uLL;
          if ( !(unsigned int)SkmiTryInsertVad(v15, v22) )
          {
            v19 = 0x800000000000LL;
            ProcessAddressSpace = -1073741800;
            *(_QWORD *)(v22 + 48) |= 0x800000000000uLL;
            goto LABEL_22;
          }
          ProcessAddressSpace = SkpsConfigureEnclave(v20, v11);
          if ( ProcessAddressSpace >= 0 )
          {
            Pool = (BCRYPT_ALG_HANDLE *)SkAllocatePool(1, 32, 1752385605);
            v20[87] = Pool;
            if ( Pool )
            {
              ProcessAddressSpace = SkpCngPrepareHashObj(L"SHA256", Pool);
              if ( ProcessAddressSpace >= 0 )
              {
                LOBYTE(v25) = 1;
                ProcessAddressSpace = SkobCreateHandle(v20, v25, 0, a8);
                if ( ProcessAddressSpace >= 0 )
                {
                  SkmiUnlockAndDereferenceVad(v22);
LABEL_29:
                  SkobDereferenceObject(v20);
                  goto LABEL_30;
                }
              }
              else
              {
                SkFreePool(1, v20[87]);
              }
            }
            else
            {
              ProcessAddressSpace = -1073741670;
            }
          }
        }
        v19 = 0x800000000000LL;
      }
LABEL_22:
      if ( v22 )
      {
        if ( (*(_QWORD *)(v22 + 48) & 0x800000000000LL) == 0 )
          SkmiDeleteVad(v15, v22);
        SkmiUnlockAndDereferenceVad(v22);
      }
LABEL_26:
      if ( !v20 )
        goto LABEL_30;
      if ( (*(_DWORD *)v20 & 2) != 0 )
      {
        LOBYTE(v19) = 1;
        SkeTerminateEnclave(v20, v19);
      }
      goto LABEL_29;
    }
  }
  return 3221225496LL;
}

```

## disassembly

```asm
0x14006b310  push    rbp
0x14006b312  push    rbx
0x14006b313  push    rsi
0x14006b314  push    rdi
0x14006b315  push    r12
0x14006b317  push    r13
0x14006b319  push    r14
0x14006b31b  push    r15
0x14006b31d  mov     rbp, rsp
0x14006b320  sub     rsp, 58h
0x14006b324  xor     edi, edi
0x14006b326  mov     r13, r9
0x14006b329  cmp     cs:SkpspEnclaveInfo, rdi
0x14006b330  mov     r12, r8
0x14006b333  mov     rsi, rdx
0x14006b336  mov     [rbp+var_20], rdi
0x14006b33a  mov     r10, rcx
0x14006b33d  mov     [rbp+var_28], rdi
0x14006b341  mov     r14d, edi
0x14006b344  mov     [rbp+var_18], rdi
0x14006b348  mov     [rbp+var_10], rdi
0x14006b34c  jz      loc_14006B64E
0x14006b352  cmp     [rbp+arg_30], dil
0x14006b356  jnz     loc_14006B64E
0x14006b35c  shr     rdx, 0Ch
0x14006b360  mov     r8d, 0FFFh
0x14006b366  test    r8d, esi
0x14006b369  mov     r9d, 1FFh
0x14006b36f  setz    cl
0x14006b372  test    r9, rdx
0x14006b375  setz    al
0x14006b378  test    al, cl
0x14006b37a  jz      loc_14006B647
0x14006b380  test    r8d, r12d
0x14006b383  jnz     loc_14006B647
0x14006b389  lea     rax, [r12-1]
0x14006b38e  add     rax, rsi
0x14006b391  shr     rax, 0Ch
0x14006b395  cmp     rax, rdx
0x14006b398  jb      loc_14006B647
0x14006b39e  inc     rax
0x14006b3a1  test    r9, rax
0x14006b3a4  jnz     loc_14006B647
0x14006b3aa  lea     r8, [rbp+var_20]
0x14006b3ae  mov     rcx, r10
0x14006b3b1  lea     edx, [rdi+1]
0x14006b3b4  call    SkpsReferenceProcessByHandle
0x14006b3b9  test    eax, eax
0x14006b3bb  js      loc_14006B653
0x14006b3c1  mov     r15, [rbp+var_20]
0x14006b3c5  mov     rcx, [r15+48h]
0x14006b3c9  call    SkmiConfigureEnclavePartition
0x14006b3ce  mov     ebx, eax
0x14006b3d0  test    eax, eax
0x14006b3d2  js      loc_14006B5E6
0x14006b3d8  mov     rcx, [rbp+arg_20]
0x14006b3dc  test    rcx, rcx
0x14006b3df  jz      short loc_14006B405
0x14006b3e1  mov     rdx, [rbp+arg_28]
0x14006b3e5  lea     r9, [rbp+var_28]
0x14006b3e9  lea     r8d, [rdi+1]
0x14006b3ed  mov     [rsp+58h+var_38], rdi
0x14006b3f2  call    SkmmMapDataTransfer
0x14006b3f7  mov     r14, [rbp+var_28]
0x14006b3fb  mov     ebx, eax
0x14006b3fd  test    eax, eax
0x14006b3ff  js      loc_14006B5D9
0x14006b405  lea     r9, [rbp+var_18]
0x14006b409  xor     r8d, r8d
0x14006b40c  lea     rdx, SkmiEnclaveType
0x14006b413  xor     ecx, ecx
0x14006b415  call    SkobCreateObjectEx
0x14006b41a  mov     rdi, [rbp+var_18]
0x14006b41e  mov     ebx, eax
0x14006b420  test    eax, eax
0x14006b422  js      loc_14006B5BC
0x14006b428  xor     edx, edx; Val
0x14006b42a  mov     r8d, 2C0h; Size
0x14006b430  mov     rcx, rdi; void *
0x14006b433  call    memset_0
0x14006b438  mov     rcx, r15
0x14006b43b  mov     [rdi+270h], r15
0x14006b442  call    SkobReferenceObject
0x14006b447  lea     rax, [rbp+var_10]
0x14006b44b  xor     r9d, r9d
0x14006b44e  lea     r8, [rdi+218h]
0x14006b455  mov     [rsp+58h+var_38], rax
0x14006b45a  mov     rdx, r12
0x14006b45d  mov     rcx, rsi
0x14006b460  call    SkmiCreateLockedVad
0x14006b465  mov     rsi, [rbp+var_10]
0x14006b469  mov     ebx, eax
0x14006b46b  mov     rdx, 800000000000h
0x14006b475  test    eax, eax
0x14006b477  js      loc_14006B59E
0x14006b47d  mov     rax, [rsi+30h]
0x14006b481  mov     rcx, 0FF93CFFFFFFFFFFFh
0x14006b48b  and     rax, rcx
0x14006b48e  mov     rcx, 10400000000000h
0x14006b498  or      rax, rcx
0x14006b49b  mov     [rsi+30h], rax
0x14006b49f  lea     rax, [rdi+260h]
0x14006b4a6  mov     qword ptr [rdi+280h], 0
0x14006b4b1  mov     qword ptr [rdi+2A8h], 0
0x14006b4bc  mov     [rax+8], rax
0x14006b4c0  mov     [rax], rax
0x14006b4c3  lea     rax, [rdi+10h]
0x14006b4c7  mov     [rdi+0F0h], r13
0x14006b4ce  or      [rsi+30h], rdx
0x14006b4d2  mov     dword ptr [rdi+4], 0
0x14006b4d9  mov     [rax+8], rax
0x14006b4dd  mov     [rax], rax
0x14006b4e0  lea     rax, [rdi+20h]
0x14006b4e4  mov     [rax+8], rax
0x14006b4e8  mov     [rax], rax
0x14006b4eb  mov     r8, [r15+48h]
0x14006b4ef  test    r8, r8
0x14006b4f2  jz      short loc_14006B4F8
0x14006b4f4  mov     r8, [r8+18h]
0x14006b4f8  mov     rdx, r15
0x14006b4fb  mov     rcx, rdi
0x14006b4fe  call    SkmmCreateProcessAddressSpace
0x14006b503  mov     ebx, eax
0x14006b505  test    eax, eax
0x14006b507  js      loc_14006B594
0x14006b50d  mov     rcx, rdi
0x14006b510  call    SkobReferenceObject
0x14006b515  mov     r12d, 1
0x14006b51b  mov     rdx, rsi
0x14006b51e  mov     [rdi+50h], r12
0x14006b522  mov     rcx, r15
0x14006b525  or      dword ptr [rdi], 203h
0x14006b52b  mov     rax, [r15+30h]
0x14006b52f  mov     [rdi+30h], rax
0x14006b533  mov     rax, 0FFFF7FFFFFFFFFFFh
0x14006b53d  and     [rsi+30h], rax
0x14006b541  call    SkmiTryInsertVad
0x14006b546  test    eax, eax
0x14006b548  jnz     short loc_14006B55F
0x14006b54a  mov     rdx, 800000000000h
0x14006b554  mov     ebx, 0C0000018h
0x14006b559  or      [rsi+30h], rdx
0x14006b55d  jmp     short loc_14006B59E
0x14006b55f  mov     rdx, r14
0x14006b562  mov     rcx, rdi
0x14006b565  call    SkpsConfigureEnclave
0x14006b56a  mov     ebx, eax
0x14006b56c  test    eax, eax
0x14006b56e  js      short loc_14006B594
0x14006b570  mov     edx, 20h ; ' '
0x14006b575  mov     r8d, 68734845h
0x14006b57b  mov     ecx, r12d
0x14006b57e  call    SkAllocatePool
0x14006b583  mov     [rdi+2B8h], rax
0x14006b58a  test    rax, rax
0x14006b58d  jnz     short loc_14006B5F5
0x14006b58f  mov     ebx, 0C000009Ah
0x14006b594  mov     rdx, 800000000000h
0x14006b59e  test    rsi, rsi
0x14006b5a1  jz      short loc_14006B5BC
0x14006b5a3  test    [rsi+30h], rdx
0x14006b5a7  jnz     short loc_14006B5B4
0x14006b5a9  mov     rdx, rsi
0x14006b5ac  mov     rcx, r15
0x14006b5af  call    SkmiDeleteVad
0x14006b5b4  mov     rcx, rsi
0x14006b5b7  call    SkmiUnlockAndDereferenceVad
0x14006b5bc  test    rdi, rdi
0x14006b5bf  jz      short loc_14006B5D9
0x14006b5c1  mov     eax, [rdi]
0x14006b5c3  test    al, 2
0x14006b5c5  jz      short loc_14006B5D1
0x14006b5c7  mov     dl, 1
0x14006b5c9  mov     rcx, rdi
0x14006b5cc  call    SkeTerminateEnclave
0x14006b5d1  mov     rcx, rdi
0x14006b5d4  call    SkobDereferenceObject
0x14006b5d9  test    r14, r14
0x14006b5dc  jz      short loc_14006B5E6
0x14006b5de  mov     rcx, r14
0x14006b5e1  call    SkmmUnmapDataTransfer
0x14006b5e6  lea     rcx, [r15+50h]
0x14006b5ea  xor     edx, edx
0x14006b5ec  call    SkReleaseRundownProtection
0x14006b5f1  mov     eax, ebx
0x14006b5f3  jmp     short loc_14006B653
0x14006b5f5  mov     rdx, rax; phAlgorithm
0x14006b5f8  lea     rcx, pszAlgId; "SHA256"
0x14006b5ff  call    SkpCngPrepareHashObj
0x14006b604  mov     ebx, eax
0x14006b606  test    eax, eax
0x14006b608  jns     short loc_14006B61E
0x14006b60a  mov     rdx, [rdi+2B8h]
0x14006b611  mov     ecx, r12d
0x14006b614  call    SkFreePool
0x14006b619  jmp     loc_14006B594
0x14006b61e  mov     r9, [rbp+arg_38]
0x14006b625  xor     r8d, r8d
0x14006b628  mov     dl, r12b
0x14006b62b  mov     rcx, rdi
0x14006b62e  call    SkobCreateHandle
0x14006b633  mov     ebx, eax
0x14006b635  test    eax, eax
0x14006b637  js      loc_14006B594
0x14006b63d  mov     rcx, rsi
0x14006b640  call    SkmiUnlockAndDereferenceVad
0x14006b645  jmp     short loc_14006B5D1
0x14006b647  mov     eax, 0C0000018h
0x14006b64c  jmp     short loc_14006B653
0x14006b64e  mov     eax, 0C00000BBh
0x14006b653  add     rsp, 58h
0x14006b657  pop     r15
0x14006b659  pop     r14
0x14006b65b  pop     r13
0x14006b65d  pop     r12
0x14006b65f  pop     rdi
0x14006b660  pop     rsi
0x14006b661  pop     rbx
0x14006b662  pop     rbp
0x14006b663  retn
```
