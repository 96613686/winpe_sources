# SmpUpdatePagefileUsageCallback

- ea: `0x1400078c0`
- end: `0x140007c9f`
- name: `SmpUpdatePagefileUsageCallback`
- size: `991`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x1400078c0`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x14000792f`
- `ntdll!NtQuerySystemInformation` at `0x140007971`
- `ntdll!NtQuerySystemInformation` at `0x1400079c8`
- `ntdll!NtQuerySystemInformation` at `0x14000792f`
- `ntdll!NtQuerySystemInformation` at `0x140007971`
- `ntdll!NtQuerySystemInformation` at `0x1400079c8`
- `ntdll!RtlAllocateHeap` at `0x1400079a6`
- `ntdll!RtlAllocateHeap` at `0x1400079a6`
- `ntdll!RtlFreeHeap` at `0x140007a0d`
- `ntdll!RtlFreeHeap` at `0x140007c75`
- `ntdll!RtlFreeHeap` at `0x140007a0d`
- `ntdll!RtlFreeHeap` at `0x140007c75`
- `ntdll!NtSetValueKey` at `0x140007b16`
- `ntdll!NtSetValueKey` at `0x140007b16`

## string_xrefs

- `0x140007b3c`: `SmpUpdatePagefileUsageCallback`

## pseudocode

```c
char SmpUpdatePagefileUsageCallback()
{
  unsigned __int64 v0; // r14
  unsigned int *Heap; // rax
  __int64 v2; // rbx
  ULONG i; // esi
  unsigned int *v4; // rdi
  NTSTATUS v5; // esi
  __int64 v6; // rsi
  __int64 v7; // rax
  unsigned int *v8; // rcx
  unsigned __int64 v9; // r9
  unsigned __int64 v10; // rcx
  int v11; // ecx
  int v12; // edx
  int v13; // ebx
  __int64 v14; // rax
  const char *v15; // r8
  __int64 v16; // rdx
  unsigned int *v17; // rcx
  __int128 v18; // xmm1
  __int64 v19; // rcx
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  unsigned __int64 v32; // rcx
  ULONG ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  __int128 SystemInformation; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v36; // [rsp+48h] [rbp-B8h]
  _OWORD v37[10]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v38; // [rsp+100h] [rbp+0h]
  __int128 v39; // [rsp+110h] [rbp+10h]
  __int128 v40; // [rsp+120h] [rbp+20h]
  __int128 v41; // [rsp+130h] [rbp+30h]

  SystemInformation = 0;
  v36 = 0;
  memset_0(v37, 0, 0xB0u);
  ReturnLength = 0;
  v0 = SmpMemorySize / (unsigned __int64)(unsigned int)dword_140030B68;
  LODWORD(Heap) = NtQuerySystemInformation(MaxSystemInfoClass|SystemFullMemoryInformation, &SystemInformation, 0x20u, 0);
  if ( (int)Heap >= 0 )
  {
    v2 = *((_QWORD *)&v36 + 1);
    if ( *((_QWORD *)&v36 + 1) > (unsigned __int64)qword_140030CC8 )
      qword_140030CC8 = *((_QWORD *)&v36 + 1);
    else
      v2 = *((_QWORD *)&SystemInformation + 1);
    LODWORD(Heap) = NtQuerySystemInformation(SystemMemoryListInformation, v37, 0xB0u, &ReturnLength);
    if ( (int)Heap >= 0 )
    {
      for ( i = 256; ; i = ReturnLength )
      {
        Heap = (unsigned int *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, i);
        v4 = Heap;
        if ( !Heap )
          break;
        v5 = NtQuerySystemInformation(SystemPageFileInformation, Heap, i, &ReturnLength);
        if ( v5 >= 0 )
        {
          v6 = 0;
          if ( ReturnLength )
          {
            v7 = *v4;
            v6 = v4[2];
            if ( (_DWORD)v7 )
            {
              v8 = v4;
              do
              {
                v8 = (unsigned int *)((char *)v8 + v7);
                v6 += v8[2];
                v7 = *v8;
              }
              while ( (_DWORD)v7 );
            }
          }
          RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v4);
          v9 = v6 + *((_QWORD *)&v38 + 1);
          v10 = 0x400000000uLL / (unsigned int)dword_140030B68 + v2;
          if ( 10 * v2 / 9uLL <= v10 )
            v10 = 10 * v2 / 9uLL;
          if ( v10 > v0 )
          {
            v32 = v10 - v0;
            if ( v32 > v9 )
              v9 = v32;
          }
          if ( v9 > 0xFFFFFFFF )
            LODWORD(v9) = -1;
          dword_140030CD4[(unsigned int)NumOfElements % 0xF0] = v9;
          v11 = 7;
          LODWORD(NumOfElements) = NumOfElements + 1;
          v12 = SmpPagefileUsage + 1;
          SmpPagefileUsage = v12;
          LOBYTE(Heap) = v12 - 1;
          if ( (unsigned int)(v12 - 1) < 7 )
            v11 = v12 - 1;
          if ( (v12 & v11) == 0 )
          {
            LODWORD(Heap) = NtSetValueKey(
                              SmpMmKey,
                              (PUNICODE_STRING)&SmpPagefileUsageValue,
                              0,
                              3u,
                              &NumOfElements,
                              0x3C4u);
            v13 = (int)Heap;
            if ( (int)Heap < 0 )
            {
              memset_0(v37, 0, 0xE0u);
              v14 = 2147483646;
              LODWORD(v40) = v13;
              v15 = "SmpUpdatePagefileUsageCallback";
              DWORD2(v41) = 893;
              v16 = 64;
              v17 = (unsigned int *)v37;
              do
              {
                if ( !v14 )
                  break;
                if ( !*v15 )
                  break;
                *(_BYTE *)v17 = *v15++;
                v17 = (unsigned int *)((char *)v17 + 1);
                --v14;
                --v16;
              }
              while ( v16 );
              Heap = (unsigned int *)((char *)v17 - 1);
              if ( v16 )
                Heap = v17;
              *(_BYTE *)Heap = 0;
              LODWORD(Heap) = _InterlockedIncrement(&dword_14002EE94) % 16;
              v18 = v37[1];
              v19 = 28LL * (int)Heap;
              *(_OWORD *)&qword_14002EE98[v19] = v37[0];
              v20 = v37[2];
              *(_OWORD *)&qword_14002EE98[v19 + 2] = v18;
              v21 = v37[3];
              *(_OWORD *)&qword_14002EE98[v19 + 4] = v20;
              v22 = v37[4];
              *(_OWORD *)&qword_14002EE98[v19 + 6] = v21;
              v23 = v37[5];
              *(_OWORD *)&qword_14002EE98[v19 + 8] = v22;
              v24 = v37[6];
              *(_OWORD *)&qword_14002EE98[v19 + 10] = v23;
              v25 = v37[7];
              *(_OWORD *)&qword_14002EE98[v19 + 12] = v24;
              v26 = v37[8];
              *(_OWORD *)&qword_14002EE98[v19 + 14] = v25;
              v27 = v37[9];
              *(_OWORD *)&qword_14002EE98[v19 + 16] = v26;
              v28 = v38;
              *(_OWORD *)&qword_14002EE98[v19 + 18] = v27;
              v29 = v39;
              *(_OWORD *)&qword_14002EE98[v19 + 20] = v28;
              v30 = v40;
              *(_OWORD *)&qword_14002EE98[v19 + 22] = v29;
              v31 = v41;
              *(_OWORD *)&qword_14002EE98[v19 + 24] = v30;
              *(_OWORD *)&qword_14002EE98[v19 + 26] = v31;
            }
          }
          return (char)Heap;
        }
        LOBYTE(Heap) = RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v4);
        if ( v5 != -1073741820 )
          return (char)Heap;
      }
    }
  }
  return (char)Heap;
}

```

## disassembly

```asm
0x1400078c0  mov     [rsp-8+arg_18], r14
0x1400078c5  push    rbp
0x1400078c6  lea     rbp, [rsp-50h]
0x1400078cb  sub     rsp, 150h
0x1400078d2  mov     rax, cs:__security_cookie
0x1400078d9  xor     rax, rsp
0x1400078dc  mov     [rbp+50h+var_10], rax
0x1400078e0  xorps   xmm0, xmm0
0x1400078e3  lea     rcx, [rsp+150h+var_F0]; void *
0x1400078e8  xor     edx, edx; Val
0x1400078ea  mov     r8d, 0B0h; Size
0x1400078f0  movups  [rsp+150h+SystemInformation], xmm0
0x1400078f5  movups  [rsp+150h+var_108], xmm0
0x1400078fa  call    memset_0
0x1400078ff  mov     ecx, cs:dword_140030B68
0x140007905  xor     edx, edx
0x140007907  mov     rax, cs:SmpMemorySize
0x14000790e  xor     r9d, r9d; ReturnLength
0x140007911  div     rcx
0x140007914  mov     r8d, 20h ; ' '; SystemInformationLength
0x14000791a  mov     [rsp+150h+ReturnLength], 0
0x140007922  lea     rdx, [rsp+150h+SystemInformation]; SystemInformation
0x140007927  mov     ecx, 7Bh ; '{'; SystemInformationClass
0x14000792c  mov     r14, rax
0x14000792f  call    cs:__imp_NtQuerySystemInformation
0x140007935  test    eax, eax
0x140007937  js      loc_140007ACE
0x14000793d  mov     [rsp+150h+arg_0], rbx
0x140007945  mov     rbx, qword ptr [rsp+150h+var_108+8]
0x14000794a  cmp     rbx, cs:qword_140030CC8
0x140007951  ja      loc_140007C57
0x140007957  mov     rbx, qword ptr [rsp+150h+SystemInformation+8]
0x14000795c  lea     r9, [rsp+150h+ReturnLength]; ReturnLength
0x140007961  mov     r8d, 0B0h; SystemInformationLength
0x140007967  lea     rdx, [rsp+150h+var_F0]; SystemInformation
0x14000796c  mov     ecx, 50h ; 'P'; SystemInformationClass
0x140007971  call    cs:__imp_NtQuerySystemInformation
0x140007977  test    eax, eax
0x140007979  js      loc_140007AC6
0x14000797f  mov     [rsp+150h+arg_8], rsi
0x140007987  mov     esi, 100h
0x14000798c  mov     [rsp+150h+arg_10], rdi
0x140007994  mov     rcx, gs:60h
0x14000799d  xor     edx, edx; Flags
0x14000799f  mov     r8d, esi; Size
0x1400079a2  mov     rcx, [rcx+30h]; HeapHandle
0x1400079a6  call    cs:__imp_RtlAllocateHeap
0x1400079ac  mov     rdi, rax
0x1400079af  test    rax, rax
0x1400079b2  jz      loc_140007AB6
0x1400079b8  lea     r9, [rsp+150h+ReturnLength]; ReturnLength
0x1400079bd  mov     r8d, esi; SystemInformationLength
0x1400079c0  mov     rdx, rax; SystemInformation
0x1400079c3  mov     ecx, 12h; SystemInformationClass
0x1400079c8  call    cs:__imp_NtQuerySystemInformation
0x1400079ce  mov     esi, eax
0x1400079d0  test    eax, eax
0x1400079d2  js      loc_140007C63
0x1400079d8  xor     esi, esi
0x1400079da  cmp     [rsp+150h+ReturnLength], esi
0x1400079de  jz      short loc_1400079FB
0x1400079e0  mov     eax, [rdi]
0x1400079e2  mov     esi, [rdi+8]
0x1400079e5  test    eax, eax
0x1400079e7  jz      short loc_1400079FB
0x1400079e9  mov     rcx, rdi
0x1400079ec  add     rcx, rax
0x1400079ef  mov     eax, [rcx+8]
0x1400079f2  add     rsi, rax
0x1400079f5  mov     eax, [rcx]
0x1400079f7  test    eax, eax
0x1400079f9  jnz     short loc_1400079EC
0x1400079fb  mov     rcx, gs:60h
0x140007a04  mov     r8, rdi; BaseAddress
0x140007a07  xor     edx, edx; Flags
0x140007a09  mov     rcx, [rcx+30h]; HeapHandle
0x140007a0d  call    cs:__imp_RtlFreeHeap
0x140007a13  mov     r9, [rbp+50h+var_48]
0x140007a17  lea     rcx, [rbx+rbx*4]
0x140007a1b  add     rcx, rcx
0x140007a1e  mov     rax, 0E38E38E38E38E38Fh
0x140007a28  mul     rcx
0x140007a2b  mov     ecx, cs:dword_140030B68
0x140007a31  mov     rax, 400000000h
0x140007a3b  mov     r8, rdx
0x140007a3e  add     r9, rsi
0x140007a41  xor     edx, edx
0x140007a43  shr     r8, 3
0x140007a47  div     rcx
0x140007a4a  lea     rcx, [rax+rbx]
0x140007a4e  cmp     r8, rcx
0x140007a51  cmovbe  rcx, r8
0x140007a55  cmp     rcx, r14
0x140007a58  ja      loc_140007C90
0x140007a5e  mov     ecx, cs:NumOfElements
0x140007a64  lea     rdi, cs:140000000h
0x140007a6b  mov     eax, 0FFFFFFFFh
0x140007a70  cmp     r9, rax
0x140007a73  cmova   r9, rax
0x140007a77  mov     eax, 88888889h
0x140007a7c  mul     ecx
0x140007a7e  shr     edx, 7
0x140007a81  imul    eax, edx, 0F0h
0x140007a87  sub     ecx, eax
0x140007a89  mov     rva dword_140030CD4[rdi+rcx*4], r9d
0x140007a91  mov     ecx, 7
0x140007a96  mov     edx, cs:SmpPagefileUsage
0x140007a9c  inc     cs:NumOfElements
0x140007aa2  inc     edx
0x140007aa4  mov     cs:SmpPagefileUsage, edx
0x140007aaa  lea     eax, [rdx-1]
0x140007aad  cmp     eax, ecx
0x140007aaf  cmovb   ecx, eax
0x140007ab2  test    ecx, edx
0x140007ab4  jz      short loc_140007AEB
0x140007ab6  mov     rsi, [rsp+150h+arg_8]
0x140007abe  mov     rdi, [rsp+150h+arg_10]
0x140007ac6  mov     rbx, [rsp+150h+arg_0]
0x140007ace  mov     rcx, [rbp+50h+var_10]
0x140007ad2  xor     rcx, rsp; StackCookie
0x140007ad5  call    __security_check_cookie
0x140007ada  mov     r14, [rsp+150h+arg_18]
0x140007ae2  add     rsp, 150h
0x140007ae9  pop     rbp
0x140007aea  retn
0x140007aeb  mov     rcx, cs:SmpMmKey; KeyHandle
0x140007af2  lea     rax, NumOfElements
0x140007af9  mov     [rsp+150h+DataSize], 3C4h; DataSize
0x140007b01  lea     rdx, SmpPagefileUsageValue; ValueName
0x140007b08  mov     r9d, 3; Type
0x140007b0e  mov     [rsp+150h+Data], rax; Data
0x140007b13  xor     r8d, r8d; TitleIndex
0x140007b16  call    cs:__imp_NtSetValueKey
0x140007b1c  mov     ebx, eax
0x140007b1e  test    eax, eax
0x140007b20  jns     short loc_140007AB6
0x140007b22  xor     edx, edx; Val
0x140007b24  lea     rcx, [rsp+150h+var_F0]; void *
0x140007b29  mov     r8d, 0E0h; Size
0x140007b2f  call    memset_0
0x140007b34  mov     eax, 7FFFFFFEh
0x140007b39  mov     dword ptr [rbp+50h+var_30], ebx
0x140007b3c  lea     r8, aSmpupdatepagef; "SmpUpdatePagefileUsageCallback"
0x140007b43  mov     [rbp+50h+var_18], 37Dh
0x140007b4a  mov     edx, 40h ; '@'
0x140007b4f  lea     rcx, [rsp+150h+var_F0]
0x140007b54  test    rax, rax
0x140007b57  jz      short loc_140007B74
0x140007b59  movzx   r9d, byte ptr [r8]
0x140007b5d  test    r9b, r9b
0x140007b60  jz      short loc_140007B74
0x140007b62  mov     [rcx], r9b
0x140007b65  inc     r8
0x140007b68  inc     rcx
0x140007b6b  dec     rax
0x140007b6e  sub     rdx, 1
0x140007b72  jnz     short loc_140007B54
0x140007b74  test    rdx, rdx
0x140007b77  lea     rax, [rcx-1]
0x140007b7b  cmovnz  rax, rcx
0x140007b7f  mov     byte ptr [rax], 0
0x140007b82  mov     eax, 1
0x140007b87  lock xadd cs:dword_14002EE94, eax
0x140007b8f  inc     eax
0x140007b91  and     eax, 8000000Fh
0x140007b96  jge     short loc_140007B9F
0x140007b98  dec     eax
0x140007b9a  or      eax, 0FFFFFFF0h
0x140007b9d  inc     eax
0x140007b9f  movaps  xmm0, [rsp+150h+var_F0]
0x140007ba4  movaps  xmm1, [rsp+150h+var_E0]
0x140007ba9  cdqe
0x140007bab  imul    rcx, rax, 0E0h
0x140007bb2  movups  xmmword ptr [rcx+rdi+2EE98h], xmm0
0x140007bba  movaps  xmm0, [rbp+50h+var_D0]
0x140007bbe  movups  xmmword ptr [rcx+rdi+2EEA8h], xmm1
0x140007bc6  movaps  xmm1, [rbp+50h+var_C0]
0x140007bca  movups  xmmword ptr [rcx+rdi+2EEB8h], xmm0
0x140007bd2  movaps  xmm0, [rbp+50h+var_B0]
0x140007bd6  movups  xmmword ptr [rcx+rdi+2EEC8h], xmm1
0x140007bde  movaps  xmm1, [rbp+50h+var_A0]
0x140007be2  movups  xmmword ptr [rcx+rdi+2EED8h], xmm0
0x140007bea  movaps  xmm0, [rbp+50h+var_90]
0x140007bee  movups  xmmword ptr [rcx+rdi+2EEE8h], xmm1
0x140007bf6  movaps  xmm1, [rbp+50h+var_80]
0x140007bfa  movups  xmmword ptr [rcx+rdi+2EEF8h], xmm0
0x140007c02  movaps  xmm0, [rbp+50h+var_70]
0x140007c06  movups  xmmword ptr [rcx+rdi+2EF08h], xmm1
0x140007c0e  movaps  xmm1, [rbp+50h+var_60]
0x140007c12  movups  xmmword ptr [rcx+rdi+2EF18h], xmm0
0x140007c1a  movaps  xmm0, xmmword ptr [rbp+0]
0x140007c1e  movups  xmmword ptr [rcx+rdi+2EF28h], xmm1
0x140007c26  movaps  xmm1, [rbp+50h+var_40]
0x140007c2a  movups  xmmword ptr [rcx+rdi+2EF38h], xmm0
0x140007c32  movaps  xmm0, [rbp+50h+var_30]
0x140007c36  movups  xmmword ptr [rcx+rdi+2EF48h], xmm1
0x140007c3e  movaps  xmm1, xmmword ptr [rbp+30h]
0x140007c42  movups  xmmword ptr [rcx+rdi+2EF58h], xmm0
0x140007c4a  movups  xmmword ptr [rcx+rdi+2EF68h], xmm1
0x140007c52  jmp     loc_140007AB6
0x140007c57  mov     cs:qword_140030CC8, rbx
0x140007c5e  jmp     loc_14000795C
0x140007c63  mov     rcx, gs:60h
0x140007c6c  mov     r8, rdi; BaseAddress
0x140007c6f  xor     edx, edx; Flags
0x140007c71  mov     rcx, [rcx+30h]; HeapHandle
0x140007c75  call    cs:__imp_RtlFreeHeap
0x140007c7b  cmp     esi, 0C0000004h
0x140007c81  jnz     loc_140007AB6
0x140007c87  mov     esi, [rsp+150h+ReturnLength]
0x140007c8b  jmp     loc_140007994
0x140007c90  sub     rcx, r14
0x140007c93  cmp     rcx, r9
0x140007c96  cmova   r9, rcx
0x140007c9a  jmp     loc_140007A5E
```
