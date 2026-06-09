# NtQueryInformationTransactionExt

- ea: `0x14001e120`
- end: `0x14001e7b0`
- name: `NtQueryInformationTransactionExt`
- size: `1680`
- prototype: `NTSTATUS __stdcall(HANDLE TransactionHandle, TRANSACTION_INFORMATION_CLASS TransactionInformationClass, PVOID TransactionInformation, ULONG TransactionInformationLength, PULONG ReturnLength)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1400024e0`
- `0x140002510`
- `0x140002640`
- `0x14000d198`
- `0x14000d238`
- `0x14000d2bc`
- `0x14001b338`
- `0x14001e120`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001e32a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001e3c0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001e516`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001e32a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001e3c0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001e516`
- `ntoskrnl!KeReleaseMutex` at `0x14001e388`
- `ntoskrnl!KeReleaseMutex` at `0x14001e3fb`
- `ntoskrnl!KeReleaseMutex` at `0x14001e54e`
- `ntoskrnl!KeReleaseMutex` at `0x14001e763`
- `ntoskrnl!KeReleaseMutex` at `0x140021762`
- `ntoskrnl!KeReleaseMutex` at `0x14001e388`
- `ntoskrnl!KeReleaseMutex` at `0x14001e3fb`
- `ntoskrnl!KeReleaseMutex` at `0x14001e54e`
- `ntoskrnl!KeReleaseMutex` at `0x14001e763`
- `ntoskrnl!KeReleaseMutex` at `0x140021762`
- `ntoskrnl!ObfDereferenceObject` at `0x14001e772`
- `ntoskrnl!ObfDereferenceObject` at `0x140021773`
- `ntoskrnl!ObfDereferenceObject` at `0x14001e772`
- `ntoskrnl!ObfDereferenceObject` at `0x140021773`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001e293`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001e293`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140021666`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140021683`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400216a0`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400216bd`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400216da`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400216f7`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140021714`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140021731`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140021790`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140021666`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140021683`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400216a0`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400216bd`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400216da`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400216f7`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140021714`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140021731`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140021790`
- `ntoskrnl!ProbeForWrite` at `0x14001e23a`
- `ntoskrnl!ProbeForWrite` at `0x14001e23a`

## pseudocode

```c
NTSTATUS __stdcall NtQueryInformationTransactionExt(
        HANDLE TransactionHandle,
        TRANSACTION_INFORMATION_CLASS TransactionInformationClass,
        PVOID TransactionInformation,
        ULONG TransactionInformationLength,
        PULONG ReturnLength)
{
  unsigned __int64 v5; // r12
  NTSTATUS result; // eax
  ULONG v9; // r8d
  KPROCESSOR_MODE v10; // r14
  unsigned int ULongFromUser; // eax
  NTSTATUS v12; // edi
  unsigned int v13; // r9d
  int v14; // eax
  char *v15; // r14
  __int32 v16; // ebx
  __int32 v17; // ebx
  __int32 v18; // ebx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int128 v21; // xmm6
  __int128 v22; // xmm7
  int v23; // edx
  char *v24; // rcx
  _QWORD *v25; // r8
  _QWORD *v26; // rax
  _QWORD *v27; // r8
  struct _KMUTANT *v28; // rbx
  __int128 v29; // xmm6
  __int128 v30; // xmm7
  __int64 v31; // rax
  unsigned int v32; // edx
  int v33; // eax
  char *v34; // rcx
  size_t v35; // r8
  void *v36; // rdx
  unsigned int v37; // ebx
  KPROCESSOR_MODE v38; // [rsp+30h] [rbp-158h]
  ULONG v39; // [rsp+34h] [rbp-154h]
  unsigned int v41; // [rsp+40h] [rbp-148h]
  int v42; // [rsp+50h] [rbp-138h]
  PVOID Object; // [rsp+60h] [rbp-128h] BYREF
  unsigned int v44; // [rsp+68h] [rbp-120h]
  _QWORD *v45; // [rsp+70h] [rbp-118h]
  __int64 v46; // [rsp+78h] [rbp-110h]
  char *v47; // [rsp+80h] [rbp-108h]
  _QWORD *v48; // [rsp+88h] [rbp-100h]
  __int128 v49; // [rsp+90h] [rbp-F8h]
  __int128 v50; // [rsp+A0h] [rbp-E8h]
  __int128 v51; // [rsp+B0h] [rbp-D8h]
  __int128 v52; // [rsp+C0h] [rbp-C8h]
  __int128 v53; // [rsp+D0h] [rbp-B8h]
  __int128 Src; // [rsp+F8h] [rbp-90h] BYREF
  __int128 v55; // [rsp+108h] [rbp-80h]
  __int128 v56; // [rsp+118h] [rbp-70h] BYREF

  v5 = TransactionInformationLength;
  v56 = 0;
  Src = 0;
  v55 = 0;
  v39 = 0;
  if ( (unsigned int)TransactionInformationClass > TransactionSuperiorEnlistmentInformation
    && TransactionInformationClass != 5 )
  {
    return -1073741821;
  }
  if ( TransactionInformationClass )
  {
    if ( TransactionInformationClass == TransactionPropertiesInformation
      || TransactionInformationClass == TransactionEnlistmentInformation )
    {
      goto LABEL_7;
    }
    if ( TransactionInformationClass != TransactionSuperiorEnlistmentInformation )
    {
      v9 = TransactionInformationClass == 5;
      goto LABEL_15;
    }
    if ( TransactionInformationLength == 32 )
    {
      v9 = 4;
      goto LABEL_15;
    }
    return -1073741820;
  }
  if ( TransactionInformationLength != 24 )
    return -1073741820;
LABEL_7:
  v9 = 4;
LABEL_15:
  v10 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v10 )
  {
    ProbeForWrite(TransactionInformation, TransactionInformationLength, v9);
    if ( ReturnLength )
    {
      ULongFromUser = RtlReadULongFromUser(ReturnLength);
      RtlWriteULongToUser(ReturnLength, ULongFromUser);
    }
  }
  Object = 0;
  result = ObReferenceObjectByHandle(TransactionHandle, 1u, (POBJECT_TYPE)TmTransactionObjectType, v10, &Object, 0);
  v12 = result;
  if ( result >= 0 )
  {
    v38 = v10;
    v13 = 0;
    v41 = 0;
    v14 = 0;
    v15 = (char *)Object;
    if ( TransactionInformationClass != 5 )
    {
      TmpAcquireTransactionMutex(Object);
      v14 = 1;
      v13 = 0;
    }
    v42 = v14;
    if ( TransactionInformationClass )
    {
      v16 = TransactionInformationClass - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( v18 )
          {
            if ( v18 == 2 )
            {
              KeWaitForSingleObject(v15 + 632, Executive, 0, 0, 0);
              if ( (unsigned int)v5 >= *((_DWORD *)v15 + 156) )
                memmove(TransactionInformation, *((const void **)v15 + 77), *((unsigned int *)v15 + 156));
              else
                v12 = -1073741789;
              v39 = *((_DWORD *)v15 + 156);
              KeReleaseMutex((PRKMUTEX)(v15 + 632), 0);
            }
          }
          else
          {
            v19 = *((_QWORD *)v15 + 30);
            if ( v19 )
            {
              KeWaitForSingleObject((PVOID)(v19 + 64), Executive, 0, 0, 0);
              v20 = *((_QWORD *)v15 + 30);
              v49 = *(_OWORD *)(v20 + 48);
              v21 = v49;
              v50 = *(_OWORD *)(*(_QWORD *)(v20 + 152) + 136LL);
              v22 = v50;
              KeReleaseMutex((PRKMUTEX)(v20 + 64), 0);
              *(_OWORD *)TransactionInformation = v21;
              *((_OWORD *)TransactionInformation + 1) = v22;
              v39 = 32;
            }
            else
            {
              v12 = -1072103329;
            }
          }
          goto LABEL_70;
        }
        if ( (unsigned int)v5 >= 0x24 )
        {
          v53 = 0;
          v23 = *((_DWORD *)v15 + 54) - 1;
          if ( !*((_QWORD *)v15 + 30) )
            v23 = *((_DWORD *)v15 + 54);
          LODWORD(v53) = v23;
          *(_OWORD *)TransactionInformation = v53;
          *((_OWORD *)TransactionInformation + 1) = 0;
          *((_DWORD *)TransactionInformation + 8) = 0;
          if ( v23 )
            v39 = 32 * v23 + 4;
          else
            v39 = 36;
          if ( (unsigned int)v5 < v39 )
            v12 = -2147483643;
          v24 = (char *)TransactionInformation + 4;
          v47 = (char *)TransactionInformation + 4;
          v25 = v15 + 200;
          v26 = (_QWORD *)*((_QWORD *)v15 + 25);
          while ( v26 != v25 )
          {
            v27 = v26 - 15;
            v45 = v27;
            v26 = (_QWORD *)*v26;
            v48 = v26;
            if ( v27 != *((_QWORD **)v15 + 30) )
            {
              v46 = 32LL * v13;
              if ( (unsigned __int64)&v24[v46 - (_QWORD)TransactionInformation + 32] > v5 )
              {
                v12 = -2147483643;
                goto LABEL_70;
              }
              v28 = (struct _KMUTANT *)(v27 + 8);
              KeWaitForSingleObject(v27 + 8, Executive, 0, 0, 0);
              v51 = *((_OWORD *)v45 + 3);
              v29 = v51;
              v52 = *(_OWORD *)(v45[19] + 136LL);
              v30 = v52;
              KeReleaseMutex(v28, 0);
              v13 = v41 + 1;
              v41 = v13;
              v44 = v13;
              v31 = v46;
              v24 = v47;
              *(_OWORD *)&v47[v46] = v29;
              *(_OWORD *)&v24[v31 + 16] = v30;
              v26 = v48;
            }
            v25 = v15 + 200;
          }
          goto LABEL_70;
        }
      }
      else if ( (unsigned int)v5 >= 0x20 )
      {
        Src = 0;
        v55 = 0;
        Src = *((_OWORD *)v15 + 18);
        LODWORD(v55) = *((_DWORD *)v15 + 126);
        DWORD1(v55) = *((unsigned __int16 *)v15 + 152);
        WORD4(v55) = 0;
        if ( v38 )
          RtlCopyToUser(TransactionInformation, &Src, 0x20u);
        else
          RtlCopyVolatileMemory(TransactionInformation, &Src, 0x20u);
        v32 = *((unsigned __int16 *)v15 + 152);
        v33 = v32 + 24;
        if ( v32 + 24 < 0x20 )
          v33 = 32;
        v39 = v33;
        if ( (unsigned int)v5 < v32 + 24 )
        {
          v12 = -2147483643;
          v32 = v5 - 24;
        }
        v34 = (char *)TransactionInformation + 24;
        v35 = v32;
        v36 = (void *)*((_QWORD *)v15 + 39);
        if ( v38 )
          RtlCopyToUser(v34, v36, v35);
        else
          RtlCopyVolatileMemory(v34, v36, v35);
        goto LABEL_70;
      }
      v12 = -1073741789;
    }
    else
    {
      v56 = *((_OWORD *)v15 + 11);
      v37 = *((_DWORD *)v15 + 126);
      if ( v38 )
        RtlCopyToUser(TransactionInformation, &v56, 0x10u);
      else
        RtlCopyVolatileMemory(TransactionInformation, &v56, 0x10u);
      if ( v38 )
        RtlWriteULongToUser((char *)TransactionInformation + 16, 1);
      else
        *((_DWORD *)TransactionInformation + 4) = 1;
      if ( v38 )
        RtlWriteULongToUser((char *)TransactionInformation + 20, v37);
      else
        *((_DWORD *)TransactionInformation + 5) = v37;
      v39 = 24;
    }
LABEL_70:
    if ( v42 )
      KeReleaseMutex((PRKMUTEX)(*((_QWORD *)v15 + 11) + 32LL), 0);
    ObfDereferenceObject(v15);
    if ( ReturnLength )
    {
      if ( v38 )
        RtlWriteULongToUser(ReturnLength, v39);
      else
        *ReturnLength = v39;
    }
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x14001e120  mov     r11, rsp
0x14001e123  push    rbx
0x14001e124  push    rsi
0x14001e125  push    rdi
0x14001e126  push    r12
0x14001e128  push    r13
0x14001e12a  push    r14
0x14001e12c  push    r15
0x14001e12e  sub     rsp, 150h
0x14001e135  movaps  xmmword ptr [r11-48h], xmm6
0x14001e13a  movaps  xmmword ptr [r11-58h], xmm7
0x14001e13f  mov     rax, cs:__security_cookie
0x14001e146  xor     rax, rsp
0x14001e149  mov     [rsp+188h+var_60], rax
0x14001e151  mov     r12d, r9d
0x14001e154  mov     r13, r8
0x14001e157  mov     ebx, edx
0x14001e159  mov     [rsp+188h+Handle], rcx
0x14001e15e  mov     rax, [rsp+188h+ReturnLength]
0x14001e166  mov     [rsp+188h+var_130], rax
0x14001e16b  xorps   xmm0, xmm0
0x14001e16e  movups  xmmword ptr [r11-70h], xmm0
0x14001e173  xorps   xmm1, xmm1
0x14001e176  movups  [rsp+188h+Src], xmm1
0x14001e17e  movups  xmmword ptr [r11-80h], xmm1
0x14001e183  xor     esi, esi
0x14001e185  mov     [rsp+188h+var_154], esi
0x14001e189  cmp     edx, 3
0x14001e18c  jbe     short loc_14001E1CA
0x14001e18e  cmp     edx, 5
0x14001e191  jz      short loc_14001E1CA
0x14001e193  mov     eax, 0C0000003h
0x14001e198  mov     rcx, [rsp+188h+var_60]
0x14001e1a0  xor     rcx, rsp; StackCookie
0x14001e1a3  call    __security_check_cookie
0x14001e1a8  lea     r11, [rsp+188h+var_38]
0x14001e1b0  movaps  xmm6, xmmword ptr [r11-10h]
0x14001e1b5  movaps  xmm7, xmmword ptr [r11-20h]
0x14001e1ba  mov     rsp, r11
0x14001e1bd  pop     r15
0x14001e1bf  pop     r14
0x14001e1c1  pop     r13
0x14001e1c3  pop     r12
0x14001e1c5  pop     rdi
0x14001e1c6  pop     rsi
0x14001e1c7  pop     rbx
0x14001e1c8  retn
0x14001e1ca  test    ebx, ebx
0x14001e1cc  jnz     short loc_14001E1DF
0x14001e1ce  cmp     r12d, 18h
0x14001e1d2  jnz     short loc_14001E1FB
0x14001e1d4  lea     edi, [rbx+1]
0x14001e1d7  mov     r8d, 4
0x14001e1dd  jmp     short loc_14001E214
0x14001e1df  mov     edi, 1
0x14001e1e4  cmp     ebx, edi
0x14001e1e6  jz      short loc_14001E1D7
0x14001e1e8  cmp     ebx, 2
0x14001e1eb  jz      short loc_14001E1D7
0x14001e1ed  cmp     ebx, 3
0x14001e1f0  jnz     short loc_14001E20A
0x14001e1f2  lea     r15d, [rdi+1Fh]
0x14001e1f6  cmp     r12d, r15d
0x14001e1f9  jz      short loc_14001E202
0x14001e1fb  mov     eax, 0C0000004h
0x14001e200  jmp     short loc_14001E198
0x14001e202  mov     r8d, 4
0x14001e208  jmp     short loc_14001E21A
0x14001e20a  mov     r8d, esi
0x14001e20d  cmp     ebx, 5
0x14001e210  cmovz   r8d, edi; Alignment
0x14001e214  mov     r15d, 20h ; ' '
0x14001e21a  mov     rax, gs:188h
0x14001e223  mov     r14b, [rax+232h]
0x14001e22a  mov     [rsp+188h+var_158], r14b
0x14001e22f  test    r14b, r14b
0x14001e232  jz      short loc_14001E26E
0x14001e234  mov     rdx, r12; Length
0x14001e237  mov     rcx, r13; Address
0x14001e23a  call    cs:__imp_ProbeForWrite
0x14001e241  nop     dword ptr [rax+rax+00h]
0x14001e246  mov     r14, [rsp+188h+var_130]
0x14001e24b  test    r14, r14
0x14001e24e  jz      short loc_14001E262
0x14001e250  mov     rcx, r14
0x14001e253  call    RtlReadULongFromUser
0x14001e258  mov     edx, eax
0x14001e25a  mov     rcx, r14
0x14001e25d  call    RtlWriteULongToUser
0x14001e262  mov     r14b, [rsp+188h+var_158]
0x14001e267  jmp     short loc_14001E26E
0x14001e269  jmp     loc_14001E198
0x14001e26e  mov     r8, cs:TmTransactionObjectType; ObjectType
0x14001e275  mov     [rsp+188h+var_128], rsi
0x14001e27a  mov     [rsp+188h+HandleInformation], rsi; HandleInformation
0x14001e27f  lea     rax, [rsp+188h+var_128]
0x14001e284  mov     [rsp+188h+Object], rax; Object
0x14001e289  mov     r9b, r14b; AccessMode
0x14001e28c  mov     edx, edi; DesiredAccess
0x14001e28e  mov     rcx, [rsp+188h+Handle]; Handle
0x14001e293  call    cs:__imp_ObReferenceObjectByHandle
0x14001e29a  nop     dword ptr [rax+rax+00h]
0x14001e29f  mov     edi, eax
0x14001e2a1  test    eax, eax
0x14001e2a3  js      loc_14001E198
0x14001e2a9  mov     [rsp+188h+var_158], r14b
0x14001e2ae  mov     r9d, esi
0x14001e2b1  mov     dword ptr [rsp+188h+var_148], esi
0x14001e2b5  mov     eax, esi
0x14001e2b7  mov     [rsp+188h+var_140], eax
0x14001e2bb  mov     r14, [rsp+188h+var_128]
0x14001e2c0  mov     [rsp+188h+Handle], r14
0x14001e2c5  cmp     ebx, 5
0x14001e2c8  jz      short loc_14001E2DE
0x14001e2ca  mov     rcx, r14
0x14001e2cd  call    TmpAcquireTransactionMutex
0x14001e2d2  mov     eax, 1
0x14001e2d7  mov     [rsp+188h+var_140], eax
0x14001e2db  mov     r9d, esi
0x14001e2de  mov     [rsp+188h+var_138], eax
0x14001e2e2  test    ebx, ebx
0x14001e2e4  jz      loc_14001E6C9
0x14001e2ea  sub     ebx, 1
0x14001e2ed  jz      loc_14001E5C0
0x14001e2f3  sub     ebx, 1
0x14001e2f6  jz      loc_14001E42E
0x14001e2fc  sub     ebx, 1
0x14001e2ff  jz      loc_14001E399
0x14001e305  cmp     ebx, 2
0x14001e308  jnz     loc_14001E754
0x14001e30e  lea     rbx, [r14+278h]
0x14001e315  mov     [rsp+188h+var_148], rbx
0x14001e31a  mov     [rsp+188h+Object], rsi; Timeout
0x14001e31f  xor     r9d, r9d; Alertable
0x14001e322  xor     r8d, r8d; WaitMode
0x14001e325  xor     edx, edx; WaitReason
0x14001e327  mov     rcx, rbx; Object
0x14001e32a  call    cs:__imp_KeWaitForSingleObject
0x14001e331  nop     dword ptr [rax+rax+00h]
0x14001e336  nop
0x14001e337  mov     eax, [r14+270h]
0x14001e33e  cmp     r12d, eax
0x14001e341  jnb     short loc_14001E34E
0x14001e343  mov     edi, 0C0000023h
0x14001e348  mov     [rsp+188h+var_13C], edi
0x14001e34c  jmp     short loc_14001E360
0x14001e34e  mov     r8, rax; Size
0x14001e351  mov     rdx, [r14+268h]; Src
0x14001e358  mov     rcx, r13; void *
0x14001e35b  call    memmove
0x14001e360  mov     eax, [r14+270h]
0x14001e367  mov     [rsp+188h+var_154], eax
0x14001e36b  jmp     short loc_14001E383
0x14001e36d  mov     edi, eax
0x14001e36f  mov     [rsp+188h+var_13C], eax
0x14001e373  xor     esi, esi
0x14001e375  lea     r15d, [rsi+20h]
0x14001e379  mov     r14, [rsp+188h+Handle]
0x14001e37e  mov     rbx, [rsp+188h+var_148]
0x14001e383  xor     edx, edx; Wait
0x14001e385  mov     rcx, rbx; Mutex
0x14001e388  call    cs:__imp_KeReleaseMutex
0x14001e38f  nop     dword ptr [rax+rax+00h]
0x14001e394  jmp     loc_14001E754
0x14001e399  mov     rcx, [r14+0F0h]
0x14001e3a0  test    rcx, rcx
0x14001e3a3  jnz     short loc_14001E3AF
0x14001e3a5  mov     edi, 0C019005Fh
0x14001e3aa  jmp     loc_14001E754
0x14001e3af  add     rcx, 40h ; '@'; Object
0x14001e3b3  mov     [rsp+188h+Object], rsi; Timeout
0x14001e3b8  xor     r9d, r9d; Alertable
0x14001e3bb  xor     r8d, r8d; WaitMode
0x14001e3be  xor     edx, edx; WaitReason
0x14001e3c0  call    cs:__imp_KeWaitForSingleObject
0x14001e3c7  nop     dword ptr [rax+rax+00h]
0x14001e3cc  mov     rcx, [r14+0F0h]
0x14001e3d3  movups  xmm6, xmmword ptr [rcx+30h]
0x14001e3d7  movups  [rsp+188h+var_F8], xmm6
0x14001e3df  mov     rax, [rcx+98h]
0x14001e3e6  movups  xmm7, xmmword ptr [rax+88h]
0x14001e3ed  movups  [rsp+188h+var_E8], xmm7
0x14001e3f5  add     rcx, 40h ; '@'; Mutex
0x14001e3f9  xor     edx, edx; Wait
0x14001e3fb  call    cs:__imp_KeReleaseMutex
0x14001e402  nop     dword ptr [rax+rax+00h]
0x14001e407  nop
0x14001e408  movups  xmmword ptr [r13+0], xmm6
0x14001e40d  movups  xmmword ptr [r13+10h], xmm7
0x14001e412  mov     [rsp+188h+var_154], r15d
0x14001e417  jmp     loc_14001E754
0x14001e41c  mov     edi, eax
0x14001e41e  xor     esi, esi
0x14001e420  lea     r15d, [rsi+20h]
0x14001e424  mov     r14, [rsp+188h+Handle]
0x14001e429  jmp     loc_14001E754
0x14001e42e  cmp     r12d, 24h ; '$'
0x14001e432  jb      loc_14001E5C5
0x14001e438  xorps   xmm1, xmm1
0x14001e43b  xor     r8d, r8d
0x14001e43e  movups  [rsp+188h+var_B8], xmm1
0x14001e446  mov     ecx, [r14+0D8h]
0x14001e44d  lea     edx, [rcx-1]
0x14001e450  cmp     [r14+0F0h], r8
0x14001e457  cmovz   edx, ecx
0x14001e45a  mov     dword ptr [rsp+188h+var_B8], edx
0x14001e461  movups  xmm0, [rsp+188h+var_B8]
0x14001e469  movups  xmmword ptr [r13+0], xmm0
0x14001e46e  movups  xmmword ptr [r13+10h], xmm1
0x14001e473  mov     [r13+20h], r8d
0x14001e477  test    edx, edx
0x14001e479  jnz     short loc_14001E485
0x14001e47b  mov     [rsp+188h+var_154], 24h ; '$'
0x14001e483  jmp     short loc_14001E48F
0x14001e485  shl     edx, 5
0x14001e488  add     edx, 4
0x14001e48b  mov     [rsp+188h+var_154], edx
0x14001e48f  mov     edx, 80000005h
0x14001e494  cmp     r12d, [rsp+188h+var_154]
0x14001e499  cmovb   edi, edx
0x14001e49c  lea     rcx, [r13+4]
0x14001e4a0  mov     [rsp+188h+var_108], rcx
0x14001e4a8  lea     r8, [r14+0C8h]
0x14001e4af  mov     rax, [r8]
0x14001e4b2  cmp     rax, r8
0x14001e4b5  jz      loc_14001E754
0x14001e4bb  lea     r8, [rax-78h]
0x14001e4bf  mov     [rsp+188h+var_118], r8
0x14001e4c4  mov     rax, [rax]
0x14001e4c7  mov     [rsp+188h+var_100], rax
0x14001e4cf  cmp     r8, [r14+0F0h]
0x14001e4d6  jnz     short loc_14001E4DD
0x14001e4d8  jmp     loc_14001E590
0x14001e4dd  mov     eax, r9d
0x14001e4e0  shl     rax, 5
0x14001e4e4  mov     [rsp+188h+var_110], rax
0x14001e4e9  sub     rax, r13
0x14001e4ec  add     rax, 20h ; ' '
0x14001e4f0  add     rcx, rax
0x14001e4f3  mov     rax, r12
0x14001e4f6  cmp     rcx, r12
0x14001e4f9  jbe     short loc_14001E502
0x14001e4fb  mov     edi, edx
0x14001e4fd  jmp     loc_14001E754
0x14001e502  lea     rbx, [r8+40h]
0x14001e506  mov     [rsp+188h+Object], rsi; Timeout
0x14001e50b  xor     r9d, r9d; Alertable
0x14001e50e  xor     r8d, r8d; WaitMode
0x14001e511  xor     edx, edx; WaitReason
0x14001e513  mov     rcx, rbx; Object
0x14001e516  call    cs:__imp_KeWaitForSingleObject
0x14001e51d  nop     dword ptr [rax+rax+00h]
0x14001e522  mov     rax, [rsp+188h+var_118]
0x14001e527  movups  xmm6, xmmword ptr [rax+30h]
0x14001e52b  movups  [rsp+188h+var_D8], xmm6
0x14001e533  mov     rax, [rax+98h]
0x14001e53a  movups  xmm7, xmmword ptr [rax+88h]
0x14001e541  movups  [rsp+188h+var_C8], xmm7
0x14001e549  xor     edx, edx; Wait
0x14001e54b  mov     rcx, rbx; Mutex
0x14001e54e  call    cs:__imp_KeReleaseMutex
0x14001e555  nop     dword ptr [rax+rax+00h]
0x14001e55a  nop
0x14001e55b  mov     r9d, dword ptr [rsp+188h+var_148]
0x14001e560  inc     r9d
0x14001e563  mov     dword ptr [rsp+188h+var_148], r9d
0x14001e568  mov     [rsp+188h+var_120], r9d
0x14001e56d  mov     rax, [rsp+188h+var_110]
0x14001e572  mov     rcx, [rsp+188h+var_108]
0x14001e57a  movups  xmmword ptr [rax+rcx], xmm6
0x14001e57e  movups  xmmword ptr [rax+rcx+10h], xmm7
0x14001e583  mov     edx, 80000005h
0x14001e588  mov     rax, [rsp+188h+var_100]
0x14001e590  lea     r8, [r14+0C8h]
0x14001e597  jmp     loc_14001E4B2
0x14001e59c  mov     edi, eax
0x14001e59e  xor     esi, esi
0x14001e5a0  lea     r15d, [rsi+20h]
0x14001e5a4  mov     r14, [rsp+188h+Handle]
0x14001e5a9  jmp     loc_14001E754
0x14001e5ae  mov     edi, eax
0x14001e5b0  xor     esi, esi
0x14001e5b2  lea     r15d, [rsi+20h]
0x14001e5b6  mov     r14, [rsp+188h+Handle]
0x14001e5bb  jmp     loc_14001E754
0x14001e5c0  cmp     r12d, r15d
0x14001e5c3  jnb     short loc_14001E5CF
0x14001e5c5  mov     edi, 0C0000023h
0x14001e5ca  jmp     loc_14001E754
0x14001e5cf  xorps   xmm0, xmm0
0x14001e5d2  movups  [rsp+188h+Src], xmm0
0x14001e5da  movups  [rsp+188h+var_80], xmm0
0x14001e5e2  mov     eax, [r14+120h]
0x14001e5e9  mov     dword ptr [rsp+188h+Src], eax
0x14001e5f0  mov     eax, [r14+124h]
0x14001e5f7  mov     dword ptr [rsp+188h+Src+4], eax
0x14001e5fe  mov     rax, [r14+128h]
0x14001e605  mov     qword ptr [rsp+188h+Src+8], rax
0x14001e60d  mov     eax, [r14+1F8h]
0x14001e614  mov     dword ptr [rsp+188h+var_80], eax
  ... truncated ...
```
