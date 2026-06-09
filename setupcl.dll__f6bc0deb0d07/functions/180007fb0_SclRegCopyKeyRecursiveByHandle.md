# SclRegCopyKeyRecursiveByHandle

- ea: `0x180007fb0`
- end: `0x1800088b4`
- name: `SclRegCopyKeyRecursiveByHandle`
- size: `2308`
- prototype: `__int64 __fastcall(__int64, void *, __int64, _WORD *, _WORD *, _DWORD *, _DWORD *)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007fb0`
- `0x1800088bc`
- `0x18000c73c`

## callees

- `0x1800014e8`
- `0x180001cd4`
- `0x180007df8`
- `0x180007ebc`
- `0x180007fb0`
- `0x180008be0`
- `0x1800091c0`
- `0x18000923c`
- `0x18000a524`
- `0x1800179c5`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180008005`
- `ntdll!RtlAllocateHeap` at `0x18000805a`
- `ntdll!RtlAllocateHeap` at `0x1800080ab`
- `ntdll!RtlAllocateHeap` at `0x180008005`
- `ntdll!RtlAllocateHeap` at `0x18000805a`
- `ntdll!RtlAllocateHeap` at `0x1800080ab`
- `ntdll!NtClose` at `0x180008474`
- `ntdll!NtClose` at `0x180008499`
- `ntdll!NtClose` at `0x180008474`
- `ntdll!NtClose` at `0x180008499`
- `ntdll!RtlFreeHeap` at `0x180008856`
- `ntdll!RtlFreeHeap` at `0x180008873`
- `ntdll!RtlFreeHeap` at `0x180008891`
- `ntdll!RtlFreeHeap` at `0x180008856`
- `ntdll!RtlFreeHeap` at `0x180008873`
- `ntdll!RtlFreeHeap` at `0x180008891`
- `ntdll!NtSetValueKey` at `0x180008742`
- `ntdll!NtSetValueKey` at `0x180008742`

## string_xrefs

- `0x1800080c2`: `SclRegCopyKeyRecursiveByHandle`
- `0x1800081bc`: `SclRegCopyKeyRecursiveByHandle`
- `0x18000831b`: `SclRegCopyKeyRecursiveByHandle`
- `0x180008388`: `SclRegCopyKeyRecursiveByHandle`
- `0x1800083e5`: `SclRegCopyKeyRecursiveByHandle`
- `0x180008451`: `SclRegCopyKeyRecursiveByHandle`
- `0x180008469`: `SclRegCopyKeyRecursiveByHandle`
- `0x180008489`: `SclRegCopyKeyRecursiveByHandle`
- `0x1800085c8`: `SclRegCopyKeyRecursiveByHandle`
- `0x180008680`: `SclRegCopyKeyRecursiveByHandle`
- `0x1800086cf`: `SclRegCopyKeyRecursiveByHandle`
- `0x18000879c`: `SclRegCopyKeyRecursiveByHandle`
- `0x18000881a`: `SclRegCopyKeyRecursiveByHandle`
- `0x1800081a5`: `(%lx): Failed to create full path for source key.`
- `0x180008266`: `(%lx): Failed to create full path for destination key.`
- `0x1800082a9`: `(%lx): Failed to open source child key`
- `0x1800082d8`: `(%lx): Failed to create destination child key`
- `0x180008301`: `(%lx): Failed to migrate security info for child key`
- `0x18000836e`: `Copying [%ws] -> [%ws]`
- `0x180008782`: `Copying [%ws] -> [%ws]`
- `0x1800083a4`: `Copying [%ws]`
- `0x1800087bb`: `Copying [%ws]`
- `0x1800083c4`: `Copying to [%ws]`
- `0x1800087db`: `Copying to [%ws]`
- `0x1800085b1`: `(%lx): Failed to create full path for source key/value.`
- `0x18000866a`: `(%lx): Failed to create full path for destination key/value.`

## pseudocode

```c
__int64 __fastcall SclRegCopyKeyRecursiveByHandle(
        __int64 a1,
        void *a2,
        __int64 a3,
        _WORD *a4,
        _WORD *a5,
        _DWORD *a6,
        _DWORD *a7)
{
  _WORD *v9; // r15
  PVOID Heap; // rax
  int v11; // r8d
  void *v12; // r11
  int v13; // ebx
  __int64 v14; // rdi
  __int64 v15; // rax
  _WORD *v16; // rax
  _WORD *v17; // r14
  _WORD *v18; // rax
  int v19; // edi
  int v20; // eax
  __int64 v21; // r13
  int v22; // edx
  int v23; // edi
  unsigned __int64 v24; // rbx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rbx
  int v28; // eax
  __int64 v29; // rcx
  int Key; // eax
  int v31; // r9d
  char *v32; // rax
  int v33; // eax
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rcx
  char *v37; // rax
  int v38; // r9d
  int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rcx
  unsigned __int64 v42; // r13
  int v43; // r12d
  int v44; // eax
  __int64 v45; // r11
  __int64 v46; // rdi
  unsigned __int64 v47; // rbx
  int v48; // eax
  __int64 v49; // rcx
  int v50; // eax
  int v51; // eax
  __int64 v52; // rcx
  char *v53; // rax
  int v54; // r9d
  __int64 *v55; // r8
  int v56; // edx
  __int64 v57; // rcx
  NTSTATUS v58; // eax
  __int64 v59; // rcx
  _WORD *v61; // [rsp+30h] [rbp-50h]
  _WORD *v62; // [rsp+30h] [rbp-50h]
  int v63; // [rsp+40h] [rbp-40h]
  _DWORD Size[3]; // [rsp+44h] [rbp-3Ch] BYREF
  int v65; // [rsp+50h] [rbp-30h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-28h] BYREF
  HANDLE v67; // [rsp+60h] [rbp-20h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int64 v69; // [rsp+78h] [rbp-8h]

  v65 = 0;
  v69 = 0;
  v9 = 0;
  Size[0] = 4120;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x1018u);
  v12 = 0;
  *(_QWORD *)&Size[1] = Heap;
  v13 = -1073741801;
  if ( Heap )
    v13 = 0;
  v14 = -1;
  if ( a4 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a4[v15] );
    *(_QWORD *)&ValueName.Length = v15 + 256;
    v16 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * (v15 + 256));
    v12 = 0;
    v17 = v16;
    if ( !v16 )
      v13 = -1073741801;
  }
  else
  {
    v17 = 0;
    *(_QWORD *)&ValueName.Length = 0;
  }
  if ( a5 )
  {
    do
      ++v14;
    while ( a5[v14] );
    v69 = v14 + 256;
    v18 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * (v14 + 256));
    v12 = 0;
    v9 = v18;
    if ( !v18 )
      v13 = -1073741801;
  }
  v19 = 0;
  v63 = 0;
  while ( v13 >= 0 )
  {
    v67 = v12;
    Handle = v12;
    v20 = SclRegEnumerateKey(a3, v19, v11, (unsigned int)&Size[1], (__int64)Size, 2, (__int64)&v65);
    v12 = 0;
    v13 = v20;
    if ( v20 == -2147483622 )
    {
      v13 = 0;
      break;
    }
    if ( v20 < 0 )
    {
      LODWORD(v61) = v20;
      v41 = a1 + 1152;
      if ( !a1 )
        v41 = 0;
      SclLogGenericMessage(
        v41,
        3,
        (int)SclEvent_Generic_Error,
        748,
        (__int64)"SclRegCopyKeyRecursiveByHandle",
        "(%lx): Failed to enumerate src keys.",
        v61);
      LODWORD(v12) = 0;
      break;
    }
    v21 = *(_QWORD *)&Size[1];
    v22 = *(_DWORD *)(*(_QWORD *)&Size[1] + 12LL);
    if ( (unsigned __int64)(unsigned int)(v22 + 16) + 2 > Size[0] )
    {
      v13 = -2147483643;
    }
    else
    {
      v23 = 0;
      *(_WORD *)((v22 & 0xFFFFFFFE) + *(_QWORD *)&Size[1] + 16LL) = 0;
      if ( v9 )
      {
        v24 = v69;
        v25 = RtlStringCchCopyW(v9, v69, a5);
        if ( v25 >= 0 )
        {
          v25 = RtlStringCchCatW(v9, v24, L"\\");
          v12 = 0;
          if ( v25 >= 0 )
          {
            v25 = RtlStringCchCatW(v9, v24, v21 + 16);
            v12 = 0;
          }
        }
        v23 = (int)v12;
        if ( v25 != -2147483643 )
          v23 = v25;
        if ( v23 < 0 )
        {
          LODWORD(v61) = v23;
          v26 = a1 + 1152;
          if ( !a1 )
            v26 = (__int64)v12;
          SclLogGenericMessage(
            v26,
            3,
            (int)SclEvent_Generic_Error,
            783,
            (__int64)"SclRegCopyKeyRecursiveByHandle",
            "(%lx): Failed to create full path for source key.",
            v61);
          v12 = 0;
        }
      }
      if ( v17 )
      {
        if ( v23 >= 0 )
        {
          v27 = *(_QWORD *)&ValueName.Length;
          v23 = RtlStringCchCopyW(v17, *(unsigned __int64 *)&ValueName.Length, a4);
          if ( v23 >= 0 )
          {
            v28 = RtlStringCchCatW(v17, v27, L"\\");
            v12 = 0;
            v23 = v28;
            if ( v28 >= 0 )
            {
              v23 = RtlStringCchCatW(v17, v27, v21 + 16);
              v12 = 0;
            }
          }
        }
        v13 = (int)v12;
        if ( v23 != -2147483643 )
          v13 = v23;
        if ( v13 < 0 )
        {
          LODWORD(v61) = v13;
          v29 = a1 + 1152;
          if ( !a1 )
            v29 = (__int64)v12;
          SclLogGenericMessage(
            v29,
            3,
            (int)SclEvent_Generic_Error,
            805,
            (__int64)"SclRegCopyKeyRecursiveByHandle",
            "(%lx): Failed to create full path for destination key.",
            v61);
LABEL_50:
          v19 = v63;
          v12 = 0;
          goto LABEL_71;
        }
LABEL_41:
        Key = SclCreateKey(a3, (const WCHAR *)(v21 + 16), 0x10F003Fu, (__int64)&v67);
        v13 = Key;
        if ( Key < 0 )
        {
          LODWORD(v61) = Key;
          v31 = 817;
          v32 = "(%lx): Failed to open source child key";
LABEL_47:
          v35 = a1 + 1152;
          if ( !a1 )
            v35 = 0;
          SclLogGenericMessage(
            v35,
            3,
            (int)SclEvent_Generic_Error,
            v31,
            (__int64)"SclRegCopyKeyRecursiveByHandle",
            v32,
            v61);
          goto LABEL_50;
        }
        v33 = SclCreateKey((__int64)a2, (const WCHAR *)(v21 + 16), 0x10F003Fu, (__int64)&Handle);
        v13 = v33;
        if ( v33 < 0 )
        {
          LODWORD(v61) = v33;
          v31 = 827;
          v32 = "(%lx): Failed to create destination child key";
          goto LABEL_47;
        }
        v34 = SclRegCopySecurityInfo(a1, v67, Handle);
        v13 = v34;
        if ( v34 < 0 )
        {
          LODWORD(v61) = v34;
          v31 = 836;
          v32 = "(%lx): Failed to migrate security info for child key";
          goto LABEL_47;
        }
        if ( a6 )
          ++*a6;
        if ( v9 )
        {
          v36 = a1 + 1152;
          if ( v17 )
          {
            if ( !a1 )
              v36 = 0;
            SclLogGenericMessage(
              v36,
              1,
              (int)SclEvent_Generic_Info,
              852,
              (__int64)"SclRegCopyKeyRecursiveByHandle",
              "Copying [%ws] -> [%ws]",
              v9,
              v17);
            goto LABEL_64;
          }
          v62 = v9;
          v37 = "Copying [%ws]";
          v38 = 859;
        }
        else
        {
          if ( !v17 )
          {
LABEL_64:
            v39 = SclRegCopyKeyRecursiveByHandle(
                    a1,
                    (_DWORD)Handle,
                    (_DWORD)v67,
                    (_DWORD)v17,
                    (__int64)v9,
                    (__int64)a6,
                    (__int64)a7);
            v13 = v39;
            if ( v39 < 0 )
            {
              LODWORD(v61) = v39;
              v40 = a1 + 1152;
              if ( !a1 )
                v40 = 0;
              SclLogGenericMessage(
                v40,
                3,
                (int)SclEvent_Generic_Error,
                876,
                (__int64)"SclRegCopyKeyRecursiveByHandle",
                "(%lx): Recursive call failed.",
                v61);
            }
            NtClose(Handle);
            goto LABEL_50;
          }
          v36 = a1 + 1152;
          v62 = v17;
          v37 = "Copying to [%ws]";
          v38 = 866;
        }
        if ( !a1 )
          v36 = 0;
        SclLogGenericMessage(
          v36,
          1,
          (int)SclEvent_Generic_Info,
          v38,
          (__int64)"SclRegCopyKeyRecursiveByHandle",
          v37,
          v62);
        goto LABEL_64;
      }
      v13 = v23;
      if ( v23 >= 0 )
        goto LABEL_41;
      v19 = v63;
    }
LABEL_71:
    if ( v67 )
    {
      NtClose(v67);
      v12 = 0;
    }
    v63 = ++v19;
  }
  v42 = *(_QWORD *)&ValueName.Length;
  v43 = (int)v12;
  while ( v13 >= 0 )
  {
    ValueName = 0;
    memset_0(*(void **)&Size[1], 0, Size[0]);
    v44 = SclRegEnumerateValueKey(a3, v43, 1, (unsigned int)&Size[1], (__int64)Size, (__int64)&v65);
    v45 = 0;
    v13 = v44;
    if ( v44 == -2147483622 )
    {
      v13 = 0;
      break;
    }
    if ( v44 < 0 )
    {
      LODWORD(v61) = v44;
      v59 = a1 + 1152;
      if ( !a1 )
        v59 = 0;
      SclLogGenericMessage(
        v59,
        3,
        (int)SclEvent_Generic_Error,
        920,
        (__int64)"SclRegCopyKeyRecursiveByHandle",
        "(%lx): Failed to enumerate source value keys.",
        v61);
      break;
    }
    v46 = *(_QWORD *)&Size[1];
    if ( v9 )
    {
      v47 = v69;
      v48 = RtlStringCchCopyW(v9, v69, a5);
      if ( v48 >= 0 )
      {
        v48 = RtlStringCchCatW(v9, v47, L"|");
        v45 = 0;
        if ( v48 >= 0 )
        {
          v48 = RtlStringCchCatW(v9, v47, v46 + 20);
          v45 = 0;
        }
      }
      v13 = v45;
      if ( v48 != -2147483643 )
        v13 = v48;
      if ( v13 < 0 )
      {
        LODWORD(v61) = v13;
        v49 = a1 + 1152;
        if ( !a1 )
          v49 = v45;
        SclLogGenericMessage(
          v49,
          3,
          (int)SclEvent_Generic_Error,
          945,
          (__int64)"SclRegCopyKeyRecursiveByHandle",
          "(%lx): Failed to create full path for source key/value.",
          v61);
        v45 = 0;
      }
    }
    if ( a4 )
    {
      if ( v13 >= 0 )
      {
        v13 = RtlStringCchCopyW(v17, v42, a4);
        if ( v13 >= 0 )
        {
          v50 = RtlStringCchCatW(v17, v42, L"|");
          v45 = 0;
          v13 = v50;
          if ( v50 >= 0 )
          {
            v13 = RtlStringCchCatW(v17, v42, v46 + 20);
            v45 = 0;
          }
        }
      }
      v51 = v45;
      if ( v13 != -2147483643 )
        v51 = v13;
      v13 = v51;
      if ( v51 < 0 )
      {
        LODWORD(v61) = v51;
        v52 = a1 + 1152;
        if ( !a1 )
          v52 = v45;
        SclLogGenericMessage(
          v52,
          3,
          (int)SclEvent_Generic_Error,
          967,
          (__int64)"SclRegCopyKeyRecursiveByHandle",
          "(%lx): Failed to create full path for destination key/value.",
          v61);
        v45 = 0;
        goto LABEL_103;
      }
    }
    else if ( v13 < 0 )
    {
      goto LABEL_103;
    }
    v13 = RtlUIntToUShort(*(unsigned int *)(v46 + 16), &ValueName);
    if ( v13 < 0 )
      goto LABEL_103;
    ValueName.Buffer = (PWSTR)(v46 + 20);
    ValueName.MaximumLength = ValueName.Length;
    if ( (unsigned int)ValueName.Length + 20 > Size[0] )
    {
      v13 = -2147483643;
LABEL_103:
      LODWORD(v61) = v13;
      v53 = "(%lx): Failed to set destination value key.";
      v54 = 1034;
      v55 = SclEvent_Generic_Error;
      v56 = 3;
      goto LABEL_104;
    }
    v58 = NtSetValueKey(
            a2,
            &ValueName,
            *(_DWORD *)v46,
            *(_DWORD *)(v46 + 4),
            (PVOID)(v46 + *(unsigned int *)(v46 + 8)),
            *(_DWORD *)(v46 + 12));
    v45 = 0;
    v13 = v58;
    if ( v58 < 0 )
      goto LABEL_103;
    if ( a7 )
      ++*a7;
    if ( !v9 )
    {
      if ( !v17 )
        goto LABEL_108;
      v61 = v17;
      v53 = "Copying to [%ws]";
      v54 = 1028;
      v55 = SclEvent_Generic_Info;
      v56 = 1;
LABEL_104:
      v57 = a1 + 1152;
LABEL_105:
      if ( !a1 )
        v57 = v45;
      SclLogGenericMessage(v57, v56, (int)v55, v54, (__int64)"SclRegCopyKeyRecursiveByHandle", v53, v61);
      goto LABEL_108;
    }
    v57 = a1 + 1152;
    v56 = 1;
    v55 = SclEvent_Generic_Info;
    if ( !v17 )
    {
      v61 = v9;
      v53 = "Copying [%ws]";
      v54 = 1021;
      goto LABEL_105;
    }
    if ( !a1 )
      v57 = 0;
    SclLogGenericMessage(
      v57,
      1,
      (int)SclEvent_Generic_Info,
      1014,
      (__int64)"SclRegCopyKeyRecursiveByHandle",
      "Copying [%ws] -> [%ws]",
      v9,
      v17);
LABEL_108:
    ++v43;
  }
  if ( v9 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  if ( v17 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
  if ( *(_QWORD *)&Size[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)&Size[1]);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180007fb0  mov     rax, rsp
0x180007fb3  mov     [rax+8], rbx
0x180007fb7  mov     [rax+20h], r9
0x180007fbb  mov     [rax+18h], r8
0x180007fbf  mov     [rax+10h], rdx
0x180007fc3  push    rbp
0x180007fc4  push    rsi
0x180007fc5  push    rdi
0x180007fc6  push    r12
0x180007fc8  push    r13
0x180007fca  push    r14
0x180007fcc  push    r15
0x180007fce  mov     rbp, rsp
0x180007fd1  sub     rsp, 80h
0x180007fd8  mov     rsi, rcx
0x180007fdb  xor     r13d, r13d
0x180007fde  mov     rcx, gs:60h
0x180007fe7  mov     r8d, 1018h; Size
0x180007fed  xor     edx, edx; Flags
0x180007fef  mov     [rbp+var_30], r13d
0x180007ff3  mov     r14, r9
0x180007ff6  mov     [rbp+var_8], r13
0x180007ffa  mov     r15d, r13d
0x180007ffd  mov     dword ptr [rbp+Size], r8d
0x180008001  mov     rcx, [rcx+30h]; HeapHandle
0x180008005  call    cs:__imp_RtlAllocateHeap
0x18000800b  xor     r11d, r11d
0x18000800e  mov     r12d, 0C0000017h
0x180008014  test    rax, rax
0x180008017  mov     qword ptr [rbp+Size+4], rax
0x18000801b  mov     ebx, r12d
0x18000801e  cmovnz  ebx, r11d
0x180008022  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180008026  test    r14, r14
0x180008029  jz      short loc_18000806F
0x18000802b  mov     rax, rdi
0x18000802e  inc     rax
0x180008031  cmp     [r14+rax*2], r11w
0x180008036  jnz     short loc_18000802E
0x180008038  mov     rcx, gs:60h
0x180008041  lea     r13, [rax+100h]
0x180008048  lea     r8, ds:0[r13*2]; Size
0x180008050  mov     qword ptr [rbp+ValueName.Length], r13
0x180008054  xor     edx, edx; Flags
0x180008056  mov     rcx, [rcx+30h]; HeapHandle
0x18000805a  call    cs:__imp_RtlAllocateHeap
0x180008060  xor     r11d, r11d
0x180008063  mov     r14, rax
0x180008066  test    rax, rax
0x180008069  cmovz   ebx, r12d
0x18000806d  jmp     short loc_180008076
0x18000806f  mov     r14, r11
0x180008072  mov     qword ptr [rbp+ValueName.Length], r11
0x180008076  mov     rax, [rbp+arg_20]
0x18000807a  test    rax, rax
0x18000807d  jz      short loc_1800080BE
0x18000807f  inc     rdi
0x180008082  cmp     [rax+rdi*2], r11w
0x180008087  jnz     short loc_18000807F
0x180008089  mov     rcx, gs:60h
0x180008092  lea     r13, [rdi+100h]
0x180008099  lea     r8, ds:0[r13*2]; Size
0x1800080a1  mov     [rbp+var_8], r13
0x1800080a5  xor     edx, edx; Flags
0x1800080a7  mov     rcx, [rcx+30h]; HeapHandle
0x1800080ab  call    cs:__imp_RtlAllocateHeap
0x1800080b1  xor     r11d, r11d
0x1800080b4  mov     r15, rax
0x1800080b7  test    rax, rax
0x1800080ba  cmovz   ebx, r12d
0x1800080be  mov     r12, [rbp+arg_28]
0x1800080c2  lea     r13, aSclregcopykeyr; "SclRegCopyKeyRecursiveByHandle"
0x1800080c9  mov     edi, r11d
0x1800080cc  mov     [rbp+var_40], r11d
0x1800080d0  test    ebx, ebx
0x1800080d2  js      loc_1800084EE
0x1800080d8  mov     rcx, [rbp+arg_10]
0x1800080dc  lea     rax, [rbp+var_30]
0x1800080e0  mov     [rsp+80h+var_50], rax
0x1800080e5  lea     r9, [rbp+Size+4]
0x1800080e9  lea     rax, [rbp+Size]
0x1800080ed  mov     [rsp+80h+DataSize], 2
0x1800080f5  mov     edx, edi
0x1800080f7  mov     [rsp+80h+Data], rax
0x1800080fc  mov     [rbp+var_20], r11
0x180008100  mov     [rbp+Handle], r11
0x180008104  call    SclRegEnumerateKey
0x180008109  xor     r11d, r11d
0x18000810c  mov     ebx, eax
0x18000810e  cmp     eax, 8000001Ah
0x180008113  jz      loc_1800084EB
0x180008119  test    eax, eax
0x18000811b  js      loc_1800084AC
0x180008121  mov     r13, qword ptr [rbp+Size+4]
0x180008125  mov     eax, dword ptr [rbp+Size]
0x180008128  mov     edx, [r13+0Ch]
0x18000812c  lea     ecx, [rdx+10h]
0x18000812f  add     rcx, 2
0x180008133  cmp     rcx, rax
0x180008136  ja      loc_180008484
0x18000813c  mov     ecx, edx
0x18000813e  mov     edi, r11d
0x180008141  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180008145  mov     [rcx+r13+10h], r11w
0x18000814b  test    r15, r15
0x18000814e  jz      loc_1800081E9
0x180008154  mov     rbx, [rbp+var_8]
0x180008158  mov     rcx, r15
0x18000815b  mov     r8, [rbp+arg_20]
0x18000815f  mov     rdx, rbx
0x180008162  call    RtlStringCchCopyW
0x180008167  test    eax, eax
0x180008169  js      short loc_180008196
0x18000816b  lea     r8, asc_180019770; "\\"
0x180008172  mov     rdx, rbx
0x180008175  mov     rcx, r15
0x180008178  call    RtlStringCchCatW
0x18000817d  xor     r11d, r11d
0x180008180  test    eax, eax
0x180008182  js      short loc_180008196
0x180008184  lea     r8, [r13+10h]
0x180008188  mov     rdx, rbx
0x18000818b  mov     rcx, r15
0x18000818e  call    RtlStringCchCatW
0x180008193  xor     r11d, r11d
0x180008196  cmp     eax, 80000005h
0x18000819b  mov     edi, r11d
0x18000819e  cmovnz  edi, eax
0x1800081a1  test    edi, edi
0x1800081a3  jns     short loc_1800081E9
0x1800081a5  lea     rax, aLxFailedToCrea_5; "(%lx): Failed to create full path for s"...
0x1800081ac  mov     dword ptr [rsp+80h+var_50], edi
0x1800081b0  mov     qword ptr [rsp+80h+DataSize], rax
0x1800081b5  lea     rcx, [rsi+480h]
0x1800081bc  lea     rax, aSclregcopykeyr; "SclRegCopyKeyRecursiveByHandle"
0x1800081c3  test    rsi, rsi
0x1800081c6  mov     r9d, 30Fh
0x1800081cc  mov     [rsp+80h+Data], rax
0x1800081d1  cmovz   rcx, r11
0x1800081d5  lea     r8, SclEvent_Generic_Error
0x1800081dc  mov     edx, 3
0x1800081e1  call    SclLogGenericMessage
0x1800081e6  xor     r11d, r11d
0x1800081e9  test    r14, r14
0x1800081ec  jz      loc_180008272
0x1800081f2  test    edi, edi
0x1800081f4  js      short loc_18000823E
0x1800081f6  mov     rbx, qword ptr [rbp+ValueName.Length]
0x1800081fa  mov     rcx, r14
0x1800081fd  mov     r8, [rbp+arg_18]
0x180008201  mov     rdx, rbx
0x180008204  call    RtlStringCchCopyW
0x180008209  mov     edi, eax
0x18000820b  test    eax, eax
0x18000820d  js      short loc_18000823E
0x18000820f  lea     r8, asc_180019770; "\\"
0x180008216  mov     rdx, rbx
0x180008219  mov     rcx, r14
0x18000821c  call    RtlStringCchCatW
0x180008221  xor     r11d, r11d
0x180008224  mov     edi, eax
0x180008226  test    eax, eax
0x180008228  js      short loc_18000823E
0x18000822a  lea     r8, [r13+10h]
0x18000822e  mov     rdx, rbx
0x180008231  mov     rcx, r14
0x180008234  call    RtlStringCchCatW
0x180008239  mov     edi, eax
0x18000823b  xor     r11d, r11d
0x18000823e  cmp     edi, 80000005h
0x180008244  mov     ebx, r11d
0x180008247  cmovnz  ebx, edi
0x18000824a  test    ebx, ebx
0x18000824c  jns     short loc_18000827C
0x18000824e  test    rsi, rsi
0x180008251  mov     dword ptr [rsp+80h+var_50], ebx
0x180008255  lea     rcx, [rsi+480h]
0x18000825c  mov     r9d, 325h
0x180008262  cmovz   rcx, r11
0x180008266  lea     rax, aLxFailedToCrea; "(%lx): Failed to create full path for d"...
0x18000826d  jmp     loc_180008316
0x180008272  mov     ebx, edi
0x180008274  test    edi, edi
0x180008276  js      loc_18000847F
0x18000827c  mov     rcx, [rbp+arg_10]
0x180008280  lea     rdi, [r13+10h]
0x180008284  mov     rdx, rdi
0x180008287  lea     r9, [rbp+var_20]
0x18000828b  mov     r8d, 10F003Fh
0x180008291  call    SclCreateKey
0x180008296  xor     r13d, r13d
0x180008299  mov     ebx, eax
0x18000829b  test    eax, eax
0x18000829d  jns     short loc_1800082B2
0x18000829f  mov     dword ptr [rsp+80h+var_50], eax
0x1800082a3  mov     r9d, 331h
0x1800082a9  lea     rax, aLxFailedToOpen_7; "(%lx): Failed to open source child key"
0x1800082b0  jmp     short loc_180008308
0x1800082b2  mov     rcx, [rbp+KeyHandle]
0x1800082b6  lea     r9, [rbp+Handle]
0x1800082ba  mov     r8d, 10F003Fh
0x1800082c0  mov     rdx, rdi
0x1800082c3  call    SclCreateKey
0x1800082c8  mov     ebx, eax
0x1800082ca  test    eax, eax
0x1800082cc  jns     short loc_1800082E1
0x1800082ce  mov     dword ptr [rsp+80h+var_50], eax
0x1800082d2  mov     r9d, 33Bh
0x1800082d8  lea     rax, aLxFailedToCrea_6; "(%lx): Failed to create destination chi"...
0x1800082df  jmp     short loc_180008308
0x1800082e1  mov     r8, [rbp+Handle]
0x1800082e5  mov     rcx, rsi
0x1800082e8  mov     rdx, [rbp+var_20]
0x1800082ec  call    SclRegCopySecurityInfo
0x1800082f1  mov     ebx, eax
0x1800082f3  test    eax, eax
0x1800082f5  jns     short loc_180008343
0x1800082f7  mov     dword ptr [rsp+80h+var_50], eax
0x1800082fb  mov     r9d, 344h
0x180008301  lea     rax, aLxFailedToMigr; "(%lx): Failed to migrate security info "...
0x180008308  test    rsi, rsi
0x18000830b  lea     rcx, [rsi+480h]
0x180008312  cmovz   rcx, r13
0x180008316  mov     qword ptr [rsp+80h+DataSize], rax
0x18000831b  lea     r13, aSclregcopykeyr; "SclRegCopyKeyRecursiveByHandle"
0x180008322  lea     r8, SclEvent_Generic_Error
0x180008329  mov     [rsp+80h+Data], r13
0x18000832e  mov     edx, 3
0x180008333  call    SclLogGenericMessage
0x180008338  mov     edi, [rbp+var_40]
0x18000833b  xor     r11d, r11d
0x18000833e  jmp     loc_180008490
0x180008343  test    r12, r12
0x180008346  jz      short loc_18000834C
0x180008348  inc     dword ptr [r12]
0x18000834c  test    r15, r15
0x18000834f  jz      short loc_1800083B3
0x180008351  lea     rcx, [rsi+480h]
0x180008358  mov     edx, 1
0x18000835d  lea     r8, SclEvent_Generic_Info
0x180008364  test    r14, r14
0x180008367  jz      short loc_18000839F
0x180008369  mov     [rsp+80h+var_48], r14
0x18000836e  lea     rax, aCopyingWsWs; "Copying [%ws] -> [%ws]"
0x180008375  mov     [rsp+80h+var_50], r15
0x18000837a  test    rsi, rsi
0x18000837d  mov     qword ptr [rsp+80h+DataSize], rax
0x180008382  mov     r9d, 354h
0x180008388  lea     rax, aSclregcopykeyr; "SclRegCopyKeyRecursiveByHandle"
0x18000838f  cmovz   rcx, r13
0x180008393  mov     [rsp+80h+Data], rax
0x180008398  call    SclLogGenericMessage
0x18000839d  jmp     short loc_1800083FA
0x18000839f  mov     [rsp+80h+var_50], r15
0x1800083a4  lea     rax, aCopyingWs; "Copying [%ws]"
0x1800083ab  mov     r9d, 35Bh
0x1800083b1  jmp     short loc_1800083DD
0x1800083b3  test    r14, r14
0x1800083b6  jz      short loc_1800083FA
0x1800083b8  lea     rcx, [rsi+480h]
0x1800083bf  mov     [rsp+80h+var_50], r14
0x1800083c4  lea     rax, aCopyingToWs; "Copying to [%ws]"
0x1800083cb  mov     r9d, 362h
0x1800083d1  lea     r8, SclEvent_Generic_Info
0x1800083d8  mov     edx, 1
0x1800083dd  mov     qword ptr [rsp+80h+DataSize], rax
0x1800083e2  test    rsi, rsi
0x1800083e5  lea     rax, aSclregcopykeyr; "SclRegCopyKeyRecursiveByHandle"
0x1800083ec  cmovz   rcx, r13
0x1800083f0  mov     [rsp+80h+Data], rax
0x1800083f5  call    SclLogGenericMessage
0x1800083fa  mov     rax, [rbp+arg_30]
0x1800083fe  mov     r9, r14
0x180008401  mov     r8, [rbp+var_20]
0x180008405  mov     rcx, rsi
0x180008408  mov     rdx, [rbp+Handle]
0x18000840c  mov     [rsp+80h+var_50], rax
0x180008411  mov     qword ptr [rsp+80h+DataSize], r12
0x180008416  mov     [rsp+80h+Data], r15
0x18000841b  call    SclRegCopyKeyRecursiveByHandle
0x180008420  mov     ebx, eax
0x180008422  test    eax, eax
0x180008424  jns     short loc_180008469
0x180008426  mov     dword ptr [rsp+80h+var_50], eax
0x18000842a  lea     rcx, [rsi+480h]
0x180008431  test    rsi, rsi
0x180008434  lea     rax, aLxRecursiveCal; "(%lx): Recursive call failed."
0x18000843b  mov     qword ptr [rsp+80h+DataSize], rax
0x180008440  lea     r8, SclEvent_Generic_Error
0x180008447  cmovz   rcx, r13
0x18000844b  mov     r9d, 36Ch
0x180008451  lea     r13, aSclregcopykeyr; "SclRegCopyKeyRecursiveByHandle"
0x180008458  mov     edx, 3
0x18000845d  mov     [rsp+80h+Data], r13
0x180008462  call    SclLogGenericMessage
0x180008467  jmp     short loc_180008470
0x180008469  lea     r13, aSclregcopykeyr; "SclRegCopyKeyRecursiveByHandle"
0x180008470  mov     rcx, [rbp+Handle]; Handle
0x180008474  call    cs:__imp_NtClose
0x18000847a  jmp     loc_180008338
  ... truncated ...
```
