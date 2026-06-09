# LCompleteTransfer_PostProcess

- ea: `0x180008910`
- end: `0x180008b4a`
- name: `LCompleteTransfer_PostProcess`
- size: `570`
- prototype: `void __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180003498`
- `0x1800064b0`
- `0x180006610`
- `0x180008910`
- `0x18001b090`
- `0x18001b12c`
- `0x18001c24c`
- `0x18001f620`
- `0x18002c8d4`
- `0x18003e15c`
- `0x18003e3b4`

## import_xrefs

- `KERNEL32!Sleep` at `0x180008b22`
- `KERNEL32!Sleep` at `0x180008b22`
- `KERNEL32!LeaveCriticalSection` at `0x180008966`
- `KERNEL32!LeaveCriticalSection` at `0x1800089d7`
- `KERNEL32!LeaveCriticalSection` at `0x180008a5a`
- `KERNEL32!LeaveCriticalSection` at `0x180008ad8`
- `KERNEL32!LeaveCriticalSection` at `0x180008966`
- `KERNEL32!LeaveCriticalSection` at `0x1800089d7`
- `KERNEL32!LeaveCriticalSection` at `0x180008a5a`
- `KERNEL32!LeaveCriticalSection` at `0x180008ad8`

## pseudocode

```c
void __fastcall LCompleteTransfer_PostProcess(__int64 a1, _DWORD *a2)
{
  unsigned __int64 v2; // rbx
  int v4; // r13d
  __int64 v6; // rcx
  unsigned int v7; // r14d
  unsigned int v8; // edx
  __int64 v9; // r15
  __int64 v10; // r12
  _DWORD *v11; // rsi
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  bool v15; // zf
  __int64 v16; // rcx

  v2 = *(_QWORD *)(a1 + 80);
  v4 = *(_DWORD *)(a1 + 88);
  if ( !(unsigned int)WaitForExclusivetCallAccess(v2, 1279345481) )
  {
LABEL_4:
    if ( !a2[7] )
      a2[7] = -2147483576;
    goto LABEL_6;
  }
  v7 = *(_DWORD *)(a1 + 112);
  if ( *(_DWORD *)(v2 + 48) != v7 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (v2 >> 4)));
    goto LABEL_4;
  }
  v9 = *(_QWORD *)(a1 + 96);
  v10 = *(_QWORD *)(a1 + 104);
  v11 = *(_DWORD **)(v2 + 8);
  if ( a2[7] )
    goto LABEL_18;
  if ( !v11 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (v2 >> 4)));
    if ( !a2[7] )
      a2[7] = -2147483605;
    goto LABEL_6;
  }
  GetCallIDs(v2);
  if ( !*(_QWORD *)(v2 + 8) )
  {
LABEL_18:
    **(_DWORD **)(v2 + 136) = 1280724553;
    v15 = *(_QWORD *)(v2 + 8) == 0;
    *(_DWORD *)v2 = 1280724553;
    if ( v15 )
    {
      v11 = 0;
    }
    else
    {
      *v11 = 1280724553;
      --*(_DWORD *)(v2 + 188);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (v2 >> 4)));
    RemoveCallFromLineList(v2);
    if ( v11 )
    {
      DereferenceObject(v16, v11[22], 1);
      RemoveCallClientFromLineClientList(v11);
    }
    SetCallConfList(v9, 0, 0);
    SetCallConfList(v10, 0, 0);
    while ( *(_DWORD *)(v2 + 188) )
      Sleep(5u);
    ServerFree(*(LPVOID *)(v2 + 136));
    FreetCall(v2);
  }
  else
  {
    v12 = v11[22];
    *a2 += 12;
    a2[8] = v12;
    a2[10] = *(_DWORD *)(v2 + 52);
    a2[11] = *(_DWORD *)(v2 + 160);
    a2[12] = *(_DWORD *)(v2 + 164);
    *(_DWORD *)v2 = 1280065859;
    *v11 = 1229734723;
    **(_DWORD **)(v2 + 136) = 1179537219;
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (v2 >> 4)));
    v14 = ReferenceObject(v13, v7, 1280065859);
    if ( v14 )
    {
      if ( v14 == v2 )
        CreateCallMonitors(v2, 0);
      DereferenceObject(v6, v7, 1);
    }
  }
LABEL_6:
  a2[9] = v4;
  v8 = *(_DWORD *)(a1 + 112);
  if ( v8 )
    DereferenceObject(v6, v8, 1);
}

```

## disassembly

```asm
0x180008910  push    rbx
0x180008912  push    rbp
0x180008913  push    rsi
0x180008914  push    rdi
0x180008915  push    r12
0x180008917  push    r13
0x180008919  push    r14
0x18000891b  push    r15
0x18000891d  sub     rsp, 28h
0x180008921  mov     rbx, [rcx+50h]
0x180008925  mov     rdi, rdx
0x180008928  mov     r13d, [rcx+58h]
0x18000892c  mov     rbp, rcx
0x18000892f  mov     rcx, rbx
0x180008932  mov     edx, 4C414349h
0x180008937  call    WaitForExclusivetCallAccess
0x18000893c  test    eax, eax
0x18000893e  jz      short loc_18000896C
0x180008940  mov     r14d, [rbp+70h]
0x180008944  cmp     [rbx+30h], r14d
0x180008948  jz      short loc_1800089A0
0x18000894a  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180008950  shr     rbx, 4
0x180008954  and     rbx, rax
0x180008957  mov     rax, cs:gLockTable
0x18000895e  lea     rcx, [rbx+rbx*4]
0x180008962  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180008966  call    cs:__imp_LeaveCriticalSection
0x18000896c  cmp     dword ptr [rdi+1Ch], 0
0x180008970  jnz     short loc_180008979
0x180008972  mov     dword ptr [rdi+1Ch], 80000048h
0x180008979  mov     [rdi+24h], r13d
0x18000897d  mov     edx, [rbp+70h]
0x180008980  test    edx, edx
0x180008982  jz      short loc_18000898F
0x180008984  mov     r8d, 1
0x18000898a  call    DereferenceObject
0x18000898f  add     rsp, 28h
0x180008993  pop     r15
0x180008995  pop     r14
0x180008997  pop     r13
0x180008999  pop     r12
0x18000899b  pop     rdi
0x18000899c  pop     rsi
0x18000899d  pop     rbp
0x18000899e  pop     rbx
0x18000899f  retn
0x1800089a0  cmp     dword ptr [rdi+1Ch], 0
0x1800089a4  mov     r15, [rbp+60h]
0x1800089a8  mov     r12, [rbp+68h]
0x1800089ac  mov     rsi, [rbx+8]
0x1800089b0  jnz     loc_180008A96
0x1800089b6  test    rsi, rsi
0x1800089b9  jnz     short loc_1800089EB
0x1800089bb  mov     eax, cs:gdwPointerToLockTableIndexBits
0x1800089c1  shr     rbx, 4
0x1800089c5  and     rbx, rax
0x1800089c8  mov     rax, cs:gLockTable
0x1800089cf  lea     rcx, [rbx+rbx*4]
0x1800089d3  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800089d7  call    cs:__imp_LeaveCriticalSection
0x1800089dd  cmp     [rdi+1Ch], esi
0x1800089e0  jnz     short loc_180008979
0x1800089e2  mov     dword ptr [rdi+1Ch], 8000002Bh
0x1800089e9  jmp     short loc_180008979
0x1800089eb  mov     rcx, rbx
0x1800089ee  call    GetCallIDs
0x1800089f3  cmp     qword ptr [rbx+8], 0
0x1800089f8  jz      loc_180008A96
0x1800089fe  mov     eax, [rsi+58h]
0x180008a01  mov     r15d, 4C4C4143h
0x180008a07  add     dword ptr [rdi], 0Ch
0x180008a0a  mov     rcx, rbx
0x180008a0d  mov     [rdi+20h], eax
0x180008a10  mov     eax, [rbx+34h]
0x180008a13  mov     [rdi+28h], eax
0x180008a16  mov     eax, [rbx+0A0h]
0x180008a1c  mov     [rdi+2Ch], eax
0x180008a1f  mov     eax, [rbx+0A4h]
0x180008a25  mov     [rdi+30h], eax
0x180008a28  shr     rcx, 4
0x180008a2c  mov     [rbx], r15d
0x180008a2f  mov     dword ptr [rsi], 494C4343h
0x180008a35  mov     rax, [rbx+88h]
0x180008a3c  mov     dword ptr [rax], 464E4F43h
0x180008a42  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180008a48  and     rcx, rax
0x180008a4b  mov     rax, cs:gLockTable
0x180008a52  lea     rcx, [rcx+rcx*4]
0x180008a56  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180008a5a  call    cs:__imp_LeaveCriticalSection
0x180008a60  mov     r8d, r15d
0x180008a63  mov     edx, r14d
0x180008a66  call    ReferenceObject
0x180008a6b  test    rax, rax
0x180008a6e  jz      loc_180008979
0x180008a74  cmp     rax, rbx
0x180008a77  jnz     short loc_180008A83
0x180008a79  xor     edx, edx
0x180008a7b  mov     rcx, rbx
0x180008a7e  call    CreateCallMonitors
0x180008a83  mov     r8d, 1
0x180008a89  mov     edx, r14d
0x180008a8c  call    DereferenceObject
0x180008a91  jmp     loc_180008979
0x180008a96  mov     rax, [rbx+88h]
0x180008a9d  mov     ecx, 4C564E49h
0x180008aa2  mov     [rax], ecx
0x180008aa4  cmp     qword ptr [rbx+8], 0
0x180008aa9  mov     [rbx], ecx
0x180008aab  jz      short loc_180008AB7
0x180008aad  mov     [rsi], ecx
0x180008aaf  dec     dword ptr [rbx+0BCh]
0x180008ab5  jmp     short loc_180008AB9
0x180008ab7  xor     esi, esi
0x180008ab9  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180008abf  mov     rdx, rbx
0x180008ac2  shr     rdx, 4
0x180008ac6  and     rdx, rax
0x180008ac9  mov     rax, cs:gLockTable
0x180008ad0  lea     rdx, [rdx+rdx*4]
0x180008ad4  lea     rcx, [rax+rdx*8]; lpCriticalSection
0x180008ad8  call    cs:__imp_LeaveCriticalSection
0x180008ade  mov     rcx, rbx
0x180008ae1  call    RemoveCallFromLineList
0x180008ae6  test    rsi, rsi
0x180008ae9  jz      short loc_180008B01
0x180008aeb  mov     edx, [rsi+58h]
0x180008aee  mov     r8d, 1
0x180008af4  call    DereferenceObject
0x180008af9  mov     rcx, rsi
0x180008afc  call    RemoveCallClientFromLineClientList
0x180008b01  xor     r8d, r8d
0x180008b04  xor     edx, edx
0x180008b06  mov     rcx, r15
0x180008b09  call    SetCallConfList
0x180008b0e  xor     r8d, r8d
0x180008b11  xor     edx, edx
0x180008b13  mov     rcx, r12
0x180008b16  call    SetCallConfList
0x180008b1b  jmp     short loc_180008B28
0x180008b1d  mov     ecx, 5; dwMilliseconds
0x180008b22  call    cs:__imp_Sleep
0x180008b28  cmp     dword ptr [rbx+0BCh], 0
0x180008b2f  jnz     short loc_180008B1D
0x180008b31  mov     rcx, [rbx+88h]; lpMem
0x180008b38  call    ServerFree
0x180008b3d  mov     rcx, rbx
0x180008b40  call    FreetCall
0x180008b45  jmp     loc_180008979
```
