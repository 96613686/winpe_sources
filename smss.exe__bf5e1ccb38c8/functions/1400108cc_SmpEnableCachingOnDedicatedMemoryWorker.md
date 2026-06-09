# SmpEnableCachingOnDedicatedMemoryWorker

- ea: `0x1400108cc`
- end: `0x140010bb2`
- name: `SmpEnableCachingOnDedicatedMemoryWorker`
- size: `742`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000f120`
- `0x1400107d0`

## callees

- `0x1400108cc`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x140010abe`
- `ntdll!NtClose` at `0x140010b85`
- `ntdll!NtClose` at `0x140010abe`
- `ntdll!NtClose` at `0x140010b85`
- `ntdll!RtlAllocateHeap` at `0x1400109db`
- `ntdll!RtlAllocateHeap` at `0x1400109db`
- `ntdll!RtlFreeHeap` at `0x140010a26`
- `ntdll!RtlFreeHeap` at `0x140010b77`
- `ntdll!RtlFreeHeap` at `0x140010a26`
- `ntdll!RtlFreeHeap` at `0x140010b77`
- `ntdll!NtQueryValueKey` at `0x140010969`
- `ntdll!NtQueryValueKey` at `0x140010969`
- `ntdll!NtManagePartition` at `0x1400109b7`
- `ntdll!NtManagePartition` at `0x140010a00`
- `ntdll!NtManagePartition` at `0x140010a7a`
- `ntdll!NtManagePartition` at `0x140010ab1`
- `ntdll!NtManagePartition` at `0x140010b26`
- `ntdll!NtManagePartition` at `0x140010b56`
- `ntdll!NtManagePartition` at `0x1400109b7`
- `ntdll!NtManagePartition` at `0x140010a00`
- `ntdll!NtManagePartition` at `0x140010a7a`
- `ntdll!NtManagePartition` at `0x140010ab1`
- `ntdll!NtManagePartition` at `0x140010b26`
- `ntdll!NtManagePartition` at `0x140010b56`

## pseudocode

```c
__int64 SmpEnableCachingOnDedicatedMemoryWorker()
{
  int v0; // ebx
  HANDLE v1; // r14
  unsigned int *Heap; // rsi
  int v3; // eax
  unsigned int *v4; // r15
  unsigned int *v5; // rdi
  unsigned __int64 v6; // r12
  SIZE_T Size; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v9; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h]
  ULONG ResultLength; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v12; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+60h] [rbp-A0h] BYREF
  __int128 KeyValueInformation; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v15[4]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v16; // [rsp+84h] [rbp-7Ch]
  unsigned __int64 v17; // [rsp+B0h] [rbp-50h]

  ResultLength = 0;
  memset_0(v15, 0, 0xF8u);
  *(_QWORD *)&ValueName.Length = 3932218;
  Handle = 0;
  v12 = 0;
  LODWORD(Size) = 0;
  ValueName.Buffer = L"DisableDedicatedMemoryCaching";
  v9 = 0;
  KeyValueInformation = 0;
  if ( NtQueryValueKey(
         SmpMmKey,
         &ValueName,
         KeyValuePartialInformationAlign64,
         &KeyValueInformation,
         0x10u,
         &ResultLength) >= 0
    && (_DWORD)KeyValueInformation == 4
    && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x100000004LL )
  {
    return (unsigned int)-1073741823;
  }
  else
  {
    v1 = 0;
    while ( 1 )
    {
      v0 = NtManagePartition(-2, 0, 9, &Size, 4);
      if ( v0 != -1073741789 )
        break;
      Heap = (unsigned int *)RtlAllocateHeap(
                               *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                               0,
                               (unsigned int)Size);
      if ( !Heap )
        return (unsigned int)-1073741670;
      v3 = NtManagePartition(-2, 0, 9, Heap, Size);
      v0 = v3;
      if ( v3 >= 0 )
      {
        v4 = 0;
        v5 = Heap;
        v6 = 0;
        while ( *v5 )
        {
          Handle = 0;
          v9 = 0;
          *(_QWORD *)&v9 = *((_QWORD *)v5 + 3);
          HIDWORD(v9) = 2031619;
          if ( (int)NtManagePartition(-2, 0, 10, &v9, 24) >= 0 )
          {
            memset_0(v15, 0, 0xF8u);
            v16 = -1;
            v0 = NtManagePartition(Handle, 0, 0, v15, 248);
            NtClose(Handle);
            if ( v0 < 0 )
              goto LABEL_23;
            if ( v17 > v6 )
            {
              v6 = v17;
              v4 = v5;
            }
          }
          v5 = (unsigned int *)((char *)v5 + *v5);
        }
        if ( v4 )
        {
          Handle = 0;
          v9 = 0;
          *(_QWORD *)&v9 = *((_QWORD *)v4 + 3);
          HIDWORD(v9) = 2031619;
          v0 = NtManagePartition(-2, 0, 10, &v9, 24);
          if ( v0 >= 0 )
          {
            v1 = Handle;
            v12 = 4;
            v0 = NtManagePartition(Handle, 0, 6, &v12, 8);
            if ( v0 >= 0 )
              v0 = 0;
          }
        }
        else
        {
          v0 = -1073741275;
        }
LABEL_23:
        RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Heap);
        if ( v1 )
          NtClose(v1);
        return (unsigned int)v0;
      }
      if ( v3 != -1073741789 )
        goto LABEL_23;
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Heap);
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1400108cc  push    rbp
0x1400108ce  push    rbx
0x1400108cf  push    rsi
0x1400108d0  push    rdi
0x1400108d1  push    r12
0x1400108d3  push    r14
0x1400108d5  push    r15
0x1400108d7  lea     rbp, [rsp-80h]
0x1400108dc  sub     rsp, 180h
0x1400108e3  mov     rax, cs:__security_cookie
0x1400108ea  xor     rax, rsp
0x1400108ed  mov     [rbp+0B0h+var_38], rax
0x1400108f1  xor     edx, edx; Val
0x1400108f3  mov     [rsp+1B0h+var_160], 0
0x1400108fb  mov     r8d, 0F8h; Size
0x140010901  lea     rcx, [rbp+0B0h+var_130]; void *
0x140010905  call    memset_0
0x14001090a  mov     rcx, cs:SmpMmKey; KeyHandle
0x140010911  lea     r9, [rsp+1B0h+KeyValueInformation]; KeyValueInformation
0x140010916  xor     eax, eax
0x140010918  mov     qword ptr [rsp+1B0h+ValueName.Length], 3C003Ah
0x140010921  mov     [rsp+1B0h+Handle], rax
0x140010926  lea     rdx, [rsp+1B0h+ValueName]; ValueName
0x14001092b  mov     [rsp+1B0h+var_158], rax
0x140010930  xorps   xmm0, xmm0
0x140010933  lea     rax, aDisablededicat; "DisableDedicatedMemoryCaching"
0x14001093a  mov     dword ptr [rsp+1B0h+Size], 0
0x140010942  mov     [rsp+1B0h+ValueName.Buffer], rax
0x140010947  mov     r8d, 4; KeyValueInformationClass
0x14001094d  lea     rax, [rsp+1B0h+var_160]
0x140010952  mov     [rsp+1B0h+ResultLength], rax; ResultLength
0x140010957  mov     [rsp+1B0h+Length], 10h; Length
0x14001095f  movups  [rsp+1B0h+var_178], xmm0
0x140010964  movups  [rsp+1B0h+KeyValueInformation], xmm0
0x140010969  call    cs:__imp_NtQueryValueKey
0x14001096f  test    eax, eax
0x140010971  js      short loc_140010992
0x140010973  cmp     dword ptr [rsp+1B0h+KeyValueInformation], 4
0x140010978  jnz     short loc_140010992
0x14001097a  cmp     dword ptr [rsp+1B0h+KeyValueInformation+4], 4
0x14001097f  jnz     short loc_140010992
0x140010981  cmp     dword ptr [rsp+1B0h+KeyValueInformation+8], 1
0x140010986  jnz     short loc_140010992
0x140010988  mov     ebx, 0C0000001h
0x14001098d  jmp     loc_140010B92
0x140010992  xor     r14d, r14d
0x140010995  mov     edi, 0C0000023h
0x14001099a  lea     r15d, [r14+9]
0x14001099e  lea     r12, [r14-2]
0x1400109a2  lea     r9, [rsp+1B0h+Size]
0x1400109a7  mov     [rsp+1B0h+Length], 4
0x1400109af  mov     r8d, r15d
0x1400109b2  xor     edx, edx
0x1400109b4  mov     rcx, r12
0x1400109b7  call    cs:__imp_NtManagePartition
0x1400109bd  mov     ebx, eax
0x1400109bf  cmp     eax, edi
0x1400109c1  jnz     loc_140010B92
0x1400109c7  mov     rcx, gs:60h
0x1400109d0  xor     edx, edx; Flags
0x1400109d2  mov     r8d, dword ptr [rsp+1B0h+Size]; Size
0x1400109d7  mov     rcx, [rcx+30h]; HeapHandle
0x1400109db  call    cs:__imp_RtlAllocateHeap
0x1400109e1  mov     rsi, rax
0x1400109e4  test    rax, rax
0x1400109e7  jz      loc_140010B8D
0x1400109ed  mov     eax, dword ptr [rsp+1B0h+Size]
0x1400109f1  mov     r9, rsi
0x1400109f4  mov     r8d, r15d
0x1400109f7  mov     [rsp+1B0h+Length], eax
0x1400109fb  xor     edx, edx
0x1400109fd  mov     rcx, r12
0x140010a00  call    cs:__imp_NtManagePartition
0x140010a06  mov     ebx, eax
0x140010a08  test    eax, eax
0x140010a0a  jns     short loc_140010A31
0x140010a0c  cmp     eax, edi
0x140010a0e  jnz     loc_140010B65
0x140010a14  mov     rcx, gs:60h
0x140010a1d  mov     r8, rsi; BaseAddress
0x140010a20  xor     edx, edx; Flags
0x140010a22  mov     rcx, [rcx+30h]; HeapHandle
0x140010a26  call    cs:__imp_RtlFreeHeap
0x140010a2c  jmp     loc_1400109A2
0x140010a31  xor     r15d, r15d
0x140010a34  mov     rdi, rsi
0x140010a37  xor     r12d, r12d
0x140010a3a  cmp     [rdi], r14d
0x140010a3d  jz      loc_140010AE3
0x140010a43  xor     edx, edx
0x140010a45  mov     [rsp+1B0h+Length], 18h
0x140010a4d  xor     eax, eax
0x140010a4f  lea     r9, [rsp+1B0h+var_178]
0x140010a54  xorps   xmm0, xmm0
0x140010a57  mov     [rsp+1B0h+Handle], rax
0x140010a5c  movups  [rsp+1B0h+var_178], xmm0
0x140010a61  mov     rax, [rdi+18h]
0x140010a65  lea     rcx, [rdx-2]
0x140010a69  lea     r8d, [rdx+0Ah]
0x140010a6d  mov     qword ptr [rsp+1B0h+var_178], rax
0x140010a72  mov     dword ptr [rsp+1B0h+var_178+0Ch], 1F0003h
0x140010a7a  call    cs:__imp_NtManagePartition
0x140010a80  test    eax, eax
0x140010a82  js      short loc_140010AD9
0x140010a84  mov     ebx, 0F8h
0x140010a89  lea     rcx, [rbp+0B0h+var_130]; void *
0x140010a8d  mov     r8d, ebx; Size
0x140010a90  xor     edx, edx; Val
0x140010a92  call    memset_0
0x140010a97  mov     rcx, [rsp+1B0h+Handle]
0x140010a9c  lea     r9, [rbp+0B0h+var_130]
0x140010aa0  xor     r8d, r8d
0x140010aa3  mov     [rbp+0B0h+var_12C], 0FFFFFFFFFFFFFFFFh
0x140010aab  xor     edx, edx
0x140010aad  mov     [rsp+1B0h+Length], ebx
0x140010ab1  call    cs:__imp_NtManagePartition
0x140010ab7  mov     rcx, [rsp+1B0h+Handle]; Handle
0x140010abc  mov     ebx, eax
0x140010abe  call    cs:__imp_NtClose
0x140010ac4  test    ebx, ebx
0x140010ac6  js      loc_140010B65
0x140010acc  cmp     [rbp+0B0h+var_100], r12
0x140010ad0  jbe     short loc_140010AD9
0x140010ad2  mov     r12, [rbp+0B0h+var_100]
0x140010ad6  mov     r15, rdi
0x140010ad9  mov     eax, [rdi]
0x140010adb  add     rdi, rax
0x140010ade  jmp     loc_140010A3A
0x140010ae3  test    r15, r15
0x140010ae6  jnz     short loc_140010AEF
0x140010ae8  mov     ebx, 0C0000225h
0x140010aed  jmp     short loc_140010B65
0x140010aef  xor     edx, edx
0x140010af1  mov     [rsp+1B0h+Length], 18h
0x140010af9  xor     eax, eax
0x140010afb  lea     r9, [rsp+1B0h+var_178]
0x140010b00  xorps   xmm0, xmm0
0x140010b03  mov     [rsp+1B0h+Handle], rax
0x140010b08  movups  [rsp+1B0h+var_178], xmm0
0x140010b0d  mov     rax, [r15+18h]
0x140010b11  lea     rcx, [rdx-2]
0x140010b15  lea     r8d, [rdx+0Ah]
0x140010b19  mov     qword ptr [rsp+1B0h+var_178], rax
0x140010b1e  mov     dword ptr [rsp+1B0h+var_178+0Ch], 1F0003h
0x140010b26  call    cs:__imp_NtManagePartition
0x140010b2c  mov     ebx, eax
0x140010b2e  test    eax, eax
0x140010b30  js      short loc_140010B65
0x140010b32  mov     r14, [rsp+1B0h+Handle]
0x140010b37  lea     r9, [rsp+1B0h+var_158]
0x140010b3c  xor     edx, edx
0x140010b3e  mov     [rsp+1B0h+var_158], 4
0x140010b47  mov     rcx, r14
0x140010b4a  mov     [rsp+1B0h+Length], 8
0x140010b52  lea     r8d, [rdx+6]
0x140010b56  call    cs:__imp_NtManagePartition
0x140010b5c  mov     ebx, eax
0x140010b5e  xor     eax, eax
0x140010b60  test    ebx, ebx
0x140010b62  cmovns  ebx, eax
0x140010b65  mov     rcx, gs:60h
0x140010b6e  mov     r8, rsi; BaseAddress
0x140010b71  xor     edx, edx; Flags
0x140010b73  mov     rcx, [rcx+30h]; HeapHandle
0x140010b77  call    cs:__imp_RtlFreeHeap
0x140010b7d  test    r14, r14
0x140010b80  jz      short loc_140010B92
0x140010b82  mov     rcx, r14; Handle
0x140010b85  call    cs:__imp_NtClose
0x140010b8b  jmp     short loc_140010B92
0x140010b8d  mov     ebx, 0C000009Ah
0x140010b92  mov     eax, ebx
0x140010b94  mov     rcx, [rbp+0B0h+var_38]
0x140010b98  xor     rcx, rsp; StackCookie
0x140010b9b  call    __security_check_cookie
0x140010ba0  add     rsp, 180h
0x140010ba7  pop     r15
0x140010ba9  pop     r14
0x140010bab  pop     r12
0x140010bad  pop     rdi
0x140010bae  pop     rsi
0x140010baf  pop     rbx
0x140010bb0  pop     rbp
0x140010bb1  retn
```
