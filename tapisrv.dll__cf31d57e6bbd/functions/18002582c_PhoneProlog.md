# PhoneProlog

- ea: `0x18002582c`
- end: `0x180025c22`
- name: `PhoneProlog`
- size: `1014`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, LPHANDLE lpTargetHandle, __int64, int, __int64, __int64, int)`
- caller_count: `26`
- callee_count: `8`
- tags: ``

## callers

- `0x1800217c0`
- `0x180021890`
- `0x180021a20`
- `0x180021c00`
- `0x180021d00`
- `0x180021f20`
- `0x180022040`
- `0x180022140`
- `0x180022210`
- `0x180022870`
- `0x1800229c0`
- `0x180022aa0`
- `0x180022b80`
- `0x180022f60`
- `0x180023800`
- `0x180023910`
- `0x1800240e0`
- `0x1800242a0`
- `0x180024420`
- `0x180024560`
- `0x1800246a0`
- `0x1800247b0`
- `0x1800248d0`
- `0x1800249e0`
- `0x180024ad0`
- `0x180024dc0`

## callees

- `0x180021640`
- `0x18002582c`
- `0x18002c8d4`
- `0x18002f660`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e2f0`
- `0x18003e3b4`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180025b80`
- `KERNEL32!HeapAlloc` at `0x180025b80`

## pseudocode

```c
__int64 __fastcall PhoneProlog(
        __int64 a1,
        int a2,
        unsigned int a3,
        _QWORD *a4,
        unsigned int *a5,
        LPHANDLE lpTargetHandle,
        _DWORD *a7,
        unsigned int a8,
        _QWORD *a9,
        _QWORD *a10,
        unsigned int a11)
{
  __int64 v15; // rcx
  unsigned int v16; // ebx
  __int64 v17; // rsi
  int v18; // r14d
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rsi
  char *PhoneLookupEntry; // rax
  HANDLE *v23; // r10
  _QWORD *v24; // r14
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rcx
  _DWORD *v30; // rax
  __int64 v31; // rcx
  _DWORD *v32; // rsi
  int v34; // [rsp+30h] [rbp-58h]
  int v35; // [rsp+34h] [rbp-54h]
  __int64 v36; // [rsp+48h] [rbp-40h]

  TRACELogPrint(0x80002u, "PhoneProlog:  -- enter");
  *lpTargetHandle = 0;
  *a7 = 0;
  if ( a10 )
    *a10 = 0;
  if ( !dword_180051928 )
  {
    v16 = -1879048158;
    goto LABEL_58;
  }
  if ( *(_QWORD *)(a1 + 56) == -1 )
  {
    v16 = -1879048157;
    goto LABEL_58;
  }
  v16 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v17 = 0;
  v18 = a2 - 1;
  if ( !v18 )
  {
    v25 = ReferenceObject(v15, a3, 1229734736);
    v27 = v25;
    if ( !v25 )
    {
      v16 = -1879048173;
LABEL_44:
      v24 = a10;
      goto LABEL_45;
    }
    if ( *(_QWORD *)(v25 + 8) == a1 )
    {
      v26 = *a5;
      if ( *(_DWORD *)(v25 + 44) < (unsigned int)v26 )
      {
        v16 = -1879048165;
        v24 = a10;
        goto LABEL_34;
      }
      v28 = *(_QWORD *)(v25 + 24);
      v17 = *(_QWORD *)(v28 + 24);
      *a4 = *(_QWORD *)(v28 + 32);
      v24 = a10;
      if ( a10 )
      {
        v34 = *(_DWORD *)(*(_QWORD *)(v27 + 16) + 16LL);
        v35 = *(_DWORD *)(v27 + 48);
        v36 = *(_QWORD *)(v27 + 24);
      }
      if ( *(_DWORD *)v27 == 1229734736 )
      {
        if ( (*(_BYTE *)(v17 + 24) & 1) != 0
          && !(unsigned int)WaitForMutex(*(HANDLE *)(v17 + 8), lpTargetHandle, 1448038992) )
        {
          v16 = -1879048164;
        }
        goto LABEL_34;
      }
    }
    else
    {
      v24 = a10;
    }
    v16 = -1879048173;
LABEL_34:
    DereferenceObject(v26, a3, 1);
    goto LABEL_45;
  }
  if ( v18 == 3 )
  {
    if ( (dword_180051900 & 2) != 0 && (*(_BYTE *)(a1 + 216) & 1) == 0 )
    {
      v15 = *a5;
      if ( (unsigned int)v15 >= *(_DWORD *)(a1 + 120) )
      {
        v16 = -1879048190;
        goto LABEL_58;
      }
      *a5 = *(_DWORD *)(*(_QWORD *)(a1 + 112) + 4 * v15);
    }
    if ( a3 )
    {
      v19 = ReferenceObject(v15, a3, 1347436880);
      v21 = 0;
      if ( v19 )
      {
        if ( *(_QWORD *)(v19 + 8) == a1 )
          v21 = v19;
        DereferenceObject(v20, a3, 1);
      }
      if ( !v21 )
      {
        v16 = -1879048185;
        goto LABEL_58;
      }
    }
    PhoneLookupEntry = GetPhoneLookupEntry(*a5);
    if ( !PhoneLookupEntry )
    {
      v16 = -1879048190;
      goto LABEL_58;
    }
    if ( *((_DWORD *)PhoneLookupEntry + 8) )
    {
      v16 = -1879048168;
      goto LABEL_58;
    }
    v17 = *((_QWORD *)PhoneLookupEntry + 3);
    if ( !v17 )
    {
      v16 = -1879048167;
      goto LABEL_58;
    }
    if ( (*(_BYTE *)(v17 + 24) & 1) != 0 )
    {
      v24 = a10;
      if ( !(unsigned int)WaitForMutex(*(HANDLE *)(v17 + 8), v23, 1448038992) )
        v16 = -1879048164;
      goto LABEL_45;
    }
    goto LABEL_44;
  }
  v24 = a10;
LABEL_45:
  if ( !v16 )
  {
    if ( !a9 || (v29 = *(_QWORD *)(v17 + 8LL * a8 + 128), (*a9 = v29) != 0) )
    {
      if ( v24 )
      {
        v30 = HeapAlloc(ghTapisrvHeap, 8u, 0x78u);
        v32 = v30;
        if ( v30 )
        {
          v16 = NewObject(v31, v30, 0);
          v32[18] = v16;
          if ( v16 )
          {
            *v32 = 1129927489;
            *((_QWORD *)v32 + 4) = a1;
            v32[15] = v34;
            v32[16] = v35;
            *((_QWORD *)v32 + 3) = v36;
            v32[14] = 0;
            if ( a11 )
              v16 = a11;
            v32[19] = v16;
            *v24 = v32;
          }
          else
          {
            ServerFree(v32);
            v16 = -2147483580;
          }
        }
        else
        {
          v16 = -1879048166;
        }
      }
    }
    else
    {
      v16 = -1879048163;
    }
  }
LABEL_58:
  TRACELogPrint(0x80002u, "PhoneProlog: exit, result=x%x", v16);
  return v16;
}

```

## disassembly

```asm
0x18002582c  mov     [rsp+arg_8], rbx
0x180025831  mov     [rsp+arg_10], r8d
0x180025836  mov     [rsp+arg_0], rcx
0x18002583b  push    rsi
0x18002583c  push    r12
0x18002583e  push    r13
0x180025840  push    r14
0x180025842  push    r15
0x180025844  sub     rsp, 60h
0x180025848  mov     r13, r9
0x18002584b  mov     r12d, r8d
0x18002584e  mov     r14d, edx
0x180025851  mov     r15, rcx
0x180025854  lea     rdx, aPhoneprologEnt; "PhoneProlog:  -- enter"
0x18002585b  mov     ecx, 80002h
0x180025860  call    TRACELogPrint
0x180025865  mov     r10, [rsp+88h+lpTargetHandle]
0x18002586d  mov     qword ptr [r10], 0
0x180025874  mov     r8, [rsp+88h+arg_30]
0x18002587c  mov     dword ptr [r8], 0
0x180025883  mov     rax, [rsp+88h+arg_48]
0x18002588b  test    rax, rax
0x18002588e  jz      short loc_180025897
0x180025890  mov     qword ptr [rax], 0
0x180025897  cmp     cs:dword_180051928, 0
0x18002589e  jnz     short loc_1800258AA
0x1800258a0  mov     ebx, 90000022h
0x1800258a5  jmp     loc_180025BF6
0x1800258aa  cmp     qword ptr [r15+38h], 0FFFFFFFFFFFFFFFFh
0x1800258af  jnz     short loc_1800258BB
0x1800258b1  mov     ebx, 90000023h
0x1800258b6  jmp     loc_180025BF6
0x1800258bb  xor     ebx, ebx
0x1800258bd  mov     [rsp+88h+var_58], ebx
0x1800258c1  mov     [rsp+88h+var_54], ebx
0x1800258c5  mov     [rsp+88h+var_40], rbx
0x1800258ca  xor     esi, esi
0x1800258cc  mov     [rsp+88h+var_48], rsi
0x1800258d1  sub     r14d, 1
0x1800258d5  jz      loc_180025A02
0x1800258db  cmp     r14d, 3
0x1800258df  jnz     loc_180025B62
0x1800258e5  test    byte ptr cs:dword_180051900, 2
0x1800258ec  jz      short loc_180025937
0x1800258ee  test    byte ptr [r15+0D8h], 1
0x1800258f6  jnz     short loc_180025937
0x1800258f8  mov     rax, [rsp+88h+arg_20]
0x180025900  mov     ecx, [rax]
0x180025902  cmp     ecx, [r15+78h]
0x180025906  jb      short loc_180025916
0x180025908  mov     ebx, 90000002h
0x18002590d  mov     [rsp+88h+var_50], ebx
0x180025911  jmp     loc_180025BF6
0x180025916  mov     rax, [r15+70h]
0x18002591a  mov     edx, [rax+rcx*4]
0x18002591d  mov     rax, [rsp+88h+arg_20]
0x180025925  mov     [rax], edx
0x180025927  jmp     short loc_180025937
0x180025929  mov     ebx, 90000013h
0x18002592e  mov     [rsp+88h+var_50], ebx
0x180025932  jmp     loc_180025BF6
0x180025937  test    r12d, r12d
0x18002593a  jz      short loc_180025986
0x18002593c  mov     r8d, 50504150h
0x180025942  mov     edx, r12d
0x180025945  call    ReferenceObject
0x18002594a  xor     esi, esi
0x18002594c  test    rax, rax
0x18002594f  jz      short loc_180025967
0x180025951  cmp     [rax+8], r15
0x180025955  cmovz   rsi, rax
0x180025959  mov     r8d, 1
0x18002595f  mov     edx, r12d
0x180025962  call    DereferenceObject
0x180025967  test    rsi, rsi
0x18002596a  jnz     short loc_180025976
0x18002596c  mov     ebx, 90000007h
0x180025971  jmp     loc_180025BF6
0x180025976  mov     r10, [rsp+88h+lpTargetHandle]
0x18002597e  mov     r8, [rsp+88h+arg_30]
0x180025986  mov     rcx, [rsp+88h+arg_20]
0x18002598e  mov     ecx, [rcx]
0x180025990  call    GetPhoneLookupEntry
0x180025995  test    rax, rax
0x180025998  jnz     short loc_1800259A4
0x18002599a  mov     ebx, 90000002h
0x18002599f  jmp     loc_180025BF6
0x1800259a4  cmp     dword ptr [rax+20h], 0
0x1800259a8  jz      short loc_1800259B4
0x1800259aa  mov     ebx, 90000018h
0x1800259af  jmp     loc_180025BF6
0x1800259b4  mov     rsi, [rax+18h]
0x1800259b8  test    rsi, rsi
0x1800259bb  jnz     short loc_1800259C7
0x1800259bd  mov     ebx, 90000019h
0x1800259c2  jmp     loc_180025BF6
0x1800259c7  test    byte ptr [rsi+18h], 1
0x1800259cb  jz      loc_180025B24
0x1800259d1  mov     [rsp+88h+var_68], 564F5250h; int
0x1800259d9  mov     r9, rsi
0x1800259dc  mov     rdx, r10; lpTargetHandle
0x1800259df  mov     rcx, [rsi+8]; hSourceHandle
0x1800259e3  call    WaitForMutex
0x1800259e8  mov     r14, [rsp+88h+arg_48]
0x1800259f0  test    eax, eax
0x1800259f2  jnz     loc_180025B2C
0x1800259f8  mov     ebx, 9000001Ch
0x1800259fd  jmp     loc_180025B2C
0x180025a02  mov     r8d, 494C4350h
0x180025a08  mov     edx, r12d
0x180025a0b  call    ReferenceObject
0x180025a10  mov     rdx, rax
0x180025a13  mov     [rsp+88h+var_38], rax
0x180025a18  test    rax, rax
0x180025a1b  jz      loc_180025B1F
0x180025a21  cmp     [rax+8], r15
0x180025a25  jz      short loc_180025A47
0x180025a27  mov     r14, [rsp+88h+arg_48]
0x180025a2f  mov     ebx, 90000013h
0x180025a34  mov     r8d, 1
0x180025a3a  mov     edx, r12d
0x180025a3d  call    DereferenceObject
0x180025a42  jmp     loc_180025B2C
0x180025a47  mov     rax, [rsp+88h+arg_20]
0x180025a4f  mov     ecx, [rax]
0x180025a51  cmp     [rdx+2Ch], ecx
0x180025a54  jnb     short loc_180025A65
0x180025a56  mov     ebx, 9000001Bh
0x180025a5b  mov     r14, [rsp+88h+arg_48]
0x180025a63  jmp     short loc_180025A34
0x180025a65  mov     rax, [rdx+18h]
0x180025a69  mov     rsi, [rax+18h]
0x180025a6d  mov     [rsp+88h+var_48], rsi
0x180025a72  mov     rax, [rax+20h]
0x180025a76  mov     [r13+0], rax
0x180025a7a  mov     r14, [rsp+88h+arg_48]
0x180025a82  test    r14, r14
0x180025a85  jz      short loc_180025AA2
0x180025a87  mov     rax, [rdx+10h]
0x180025a8b  mov     eax, [rax+10h]
0x180025a8e  mov     [rsp+88h+var_58], eax
0x180025a92  mov     eax, [rdx+30h]
0x180025a95  mov     [rsp+88h+var_54], eax
0x180025a99  mov     rax, [rdx+18h]
0x180025a9d  mov     [rsp+88h+var_40], rax
0x180025aa2  jmp     short loc_180025ACB
0x180025aa4  mov     ebx, 90000013h
0x180025aa9  mov     r12d, [rsp+88h+arg_10]
0x180025ab1  mov     r15, [rsp+88h+arg_0]
0x180025ab9  mov     rsi, [rsp+88h+var_48]
0x180025abe  mov     rdx, [rsp+88h+var_38]
0x180025ac3  mov     r14, [rsp+88h+arg_48]
0x180025acb  test    ebx, ebx
0x180025acd  jnz     loc_180025A2F
0x180025ad3  cmp     dword ptr [rdx], 494C4350h
0x180025ad9  jnz     loc_180025A2F
0x180025adf  test    byte ptr [rsi+18h], 1
0x180025ae3  jz      loc_180025A34
0x180025ae9  mov     [rsp+88h+var_68], 564F5250h; int
0x180025af1  mov     r9, rsi
0x180025af4  mov     r8, [rsp+88h+arg_30]
0x180025afc  mov     rdx, [rsp+88h+lpTargetHandle]; lpTargetHandle
0x180025b04  mov     rcx, [rsi+8]; hSourceHandle
0x180025b08  call    WaitForMutex
0x180025b0d  test    eax, eax
0x180025b0f  jnz     loc_180025A34
0x180025b15  mov     ebx, 9000001Ch
0x180025b1a  jmp     loc_180025A34
0x180025b1f  mov     ebx, 90000013h
0x180025b24  mov     r14, [rsp+88h+arg_48]
0x180025b2c  test    ebx, ebx
0x180025b2e  jnz     loc_180025BF6
0x180025b34  mov     rdx, [rsp+88h+arg_40]
0x180025b3c  test    rdx, rdx
0x180025b3f  jz      short loc_180025B67
0x180025b41  mov     eax, [rsp+88h+arg_38]
0x180025b48  mov     rcx, [rsi+rax*8+80h]
0x180025b50  mov     [rdx], rcx
0x180025b53  test    rcx, rcx
0x180025b56  jnz     short loc_180025B67
0x180025b58  mov     ebx, 9000001Dh
0x180025b5d  jmp     loc_180025BF6
0x180025b62  mov     r14, rax
0x180025b65  jmp     short loc_180025B2C
0x180025b67  test    r14, r14
0x180025b6a  jz      loc_180025BF6
0x180025b70  mov     edx, 8; dwFlags
0x180025b75  lea     r8d, [rdx+70h]; dwBytes
0x180025b79  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180025b80  call    cs:__imp_HeapAlloc
0x180025b86  mov     rsi, rax
0x180025b89  test    rax, rax
0x180025b8c  jnz     short loc_180025B95
0x180025b8e  mov     ebx, 9000001Ah
0x180025b93  jmp     short loc_180025BF6
0x180025b95  xor     r8d, r8d
0x180025b98  mov     rdx, rsi
0x180025b9b  call    NewObject
0x180025ba0  mov     ebx, eax
0x180025ba2  mov     [rsi+48h], eax
0x180025ba5  test    eax, eax
0x180025ba7  jnz     short loc_180025BB8
0x180025ba9  mov     rcx, rsi; lpMem
0x180025bac  call    ServerFree
0x180025bb1  mov     ebx, 80000044h
0x180025bb6  jmp     short loc_180025BF6
0x180025bb8  mov     dword ptr [rsi], 43595341h
0x180025bbe  mov     [rsi+20h], r15
0x180025bc2  mov     eax, [rsp+88h+var_58]
0x180025bc6  mov     [rsi+3Ch], eax
0x180025bc9  mov     eax, [rsp+88h+var_54]
0x180025bcd  mov     [rsi+40h], eax
0x180025bd0  mov     rax, [rsp+88h+var_40]
0x180025bd5  mov     [rsi+18h], rax
0x180025bd9  mov     dword ptr [rsi+38h], 0
0x180025be0  cmp     [rsp+88h+arg_50], 0
0x180025be8  cmovnz  ebx, [rsp+88h+arg_50]
0x180025bf0  mov     [rsi+4Ch], ebx
0x180025bf3  mov     [r14], rsi
0x180025bf6  mov     r8d, ebx
0x180025bf9  lea     rdx, aPhoneprologExi; "PhoneProlog: exit, result=x%x"
0x180025c00  mov     ecx, 80002h
0x180025c05  call    TRACELogPrint
0x180025c0a  mov     eax, ebx
0x180025c0c  mov     rbx, [rsp+88h+arg_8]
0x180025c14  add     rsp, 60h
0x180025c18  pop     r15
0x180025c1a  pop     r14
0x180025c1c  pop     r13
0x180025c1e  pop     r12
0x180025c20  pop     rsi
0x180025c21  retn
```
