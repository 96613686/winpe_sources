# WerpCheckSpaceAvailableFull

- ea: `0x14000d68c`
- end: `0x14000d9e3`
- name: `WerpCheckSpaceAvailableFull`
- size: `855`
- prototype: `unsigned int *__fastcall(HANDLE KeyHandle, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000e464`

## callees

- `0x14000d174`
- `0x14000d68c`
- `0x14000da6c`
- `0x14000f3e0`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000d735`
- `ntoskrnl!DbgPrintEx` at `0x14000d796`
- `ntoskrnl!DbgPrintEx` at `0x14000d855`
- `ntoskrnl!DbgPrintEx` at `0x14000d8ed`
- `ntoskrnl!DbgPrintEx` at `0x14000d909`
- `ntoskrnl!DbgPrintEx` at `0x14000d950`
- `ntoskrnl!DbgPrintEx` at `0x14000d9ba`
- `ntoskrnl!DbgPrintEx` at `0x14000d735`
- `ntoskrnl!DbgPrintEx` at `0x14000d796`
- `ntoskrnl!DbgPrintEx` at `0x14000d855`
- `ntoskrnl!DbgPrintEx` at `0x14000d8ed`
- `ntoskrnl!DbgPrintEx` at `0x14000d909`
- `ntoskrnl!DbgPrintEx` at `0x14000d950`
- `ntoskrnl!DbgPrintEx` at `0x14000d9ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d883`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d961`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d883`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d961`
- `ntoskrnl!ZwClose` at `0x14000d7af`
- `ntoskrnl!ZwClose` at `0x14000d86a`
- `ntoskrnl!ZwClose` at `0x14000d91e`
- `ntoskrnl!ZwClose` at `0x14000d7af`
- `ntoskrnl!ZwClose` at `0x14000d86a`
- `ntoskrnl!ZwClose` at `0x14000d91e`
- `ntoskrnl!ZwQueryKey` at `0x14000d7e2`
- `ntoskrnl!ZwQueryKey` at `0x14000d82b`
- `ntoskrnl!ZwQueryKey` at `0x14000d7e2`
- `ntoskrnl!ZwQueryKey` at `0x14000d82b`
- `ntoskrnl!ZwEnumerateKey` at `0x14000d70a`
- `ntoskrnl!ZwEnumerateKey` at `0x14000d8c3`
- `ntoskrnl!ZwEnumerateKey` at `0x14000d70a`
- `ntoskrnl!ZwEnumerateKey` at `0x14000d8c3`

## string_xrefs

- `0x14000d78a`: `WERKERNELHOST: WerpCheckSpaceAvailableFull: Failed to open key %ws\n`

## pseudocode

```c
unsigned int *__fastcall WerpCheckSpaceAvailableFull(HANDLE KeyHandle, _DWORD *a2)
{
  unsigned int *result; // rax
  unsigned int *v5; // r14
  unsigned int v6; // r15d
  ULONG v7; // r12d
  unsigned int v8; // r13d
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  ULONG v11; // eax
  unsigned __int64 v12; // rcx
  NTSTATUS v13; // eax
  __int64 v14; // rdx
  _DWORD *Mem; // rsi
  NTSTATUS v16; // eax
  int v17; // r12d
  int v18; // eax
  unsigned int v19; // [rsp+30h] [rbp-10h] BYREF
  ULONG v20; // [rsp+34h] [rbp-Ch]
  HANDLE Handle; // [rsp+38h] [rbp-8h] BYREF
  ULONG v23; // [rsp+90h] [rbp+50h] BYREF
  ULONG ResultLength; // [rsp+98h] [rbp+58h] BYREF

  v23 = 0;
  ResultLength = 0;
  Handle = 0;
  v19 = 0;
  result = (unsigned int *)WerpAllocateMem(56, a2);
  v5 = result;
  if ( result )
  {
    v6 = dword_1400093C8;
    v7 = 0;
    v8 = 0;
    v9 = ZwEnumerateKey(KeyHandle, 0, KeyBasicInformation, result, 0x36u, &ResultLength);
    v10 = 1;
    while ( v9 != -2147483622 )
    {
      if ( v9 >= 0 )
      {
        v11 = v7 + 1;
        if ( v7 + 1 < v7 )
          break;
        v12 = (unsigned __int64)v5[3] >> 1;
        ++v7;
        v20 = v11;
        *((_WORD *)v5 + v12 + 8) = 0;
        if ( (int)WerpGetRegistryKey(KeyHandle, v5 + 4, 131097, &Handle) >= 0 )
        {
          v13 = ZwQueryKey(Handle, KeyFullInformation, 0, 0, &v23);
          if ( v13 != -2147483643 && v13 != -1073741789 )
          {
            DbgPrintEx(
              5u,
              1u,
              "WERKERNELHOST: WerpCheckSpaceAvailableFull: ZwQueryKey failed while determining the size with 0x%x\n",
              v13);
            break;
          }
          Mem = (_DWORD *)WerpAllocateMem(v23, v14);
          if ( !Mem )
          {
            DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpCheckSpaceAvailableFull: Out of memory\n");
            if ( Handle )
            {
              ZwClose(Handle);
              Handle = 0;
            }
            break;
          }
          v16 = ZwQueryKey(Handle, KeyFullInformation, Mem, v23, &v23);
          v17 = v16;
          if ( v16 < 0 )
            DbgPrintEx(5u, 1u, "WERKERNELHOST: ZwQueryKey failed with 0x%x\n", v16);
          else
            v8 += Mem[5];
          if ( Handle )
          {
            ZwClose(Handle);
            Handle = 0;
          }
          ExFreePoolWithTag(Mem, 0);
          if ( v17 < 0 || v8 > v6 )
            break;
          v7 = v20;
        }
        else
        {
          DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpCheckSpaceAvailableFull: Failed to open key %ws\n", v5 + 4);
          if ( Handle )
          {
            ZwClose(Handle);
            Handle = 0;
          }
        }
      }
      else
      {
        DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpCheckSpaceAvailableFull: ZwEnumerateKey returned status 0x%X\n", v9);
      }
      v9 = ZwEnumerateKey(KeyHandle, v7, KeyBasicInformation, v5, 0x36u, &ResultLength);
    }
    v18 = WerpCountFullDump(&v19);
    if ( v18 < 0 )
      DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpCountFullDump failed with 0x%x\n", v18);
    ExFreePoolWithTag(v5, 0);
    if ( v6 )
    {
      if ( v8 <= v6 )
      {
        if ( v19 < v6 )
          return (unsigned int *)v10;
        if ( a2 )
          *a2 = 33;
        DbgPrintEx(5u, 1u, "WERKERNELHOST: Full live kernel dump count exceeded\n");
      }
      else
      {
        if ( a2 )
          *a2 = 32;
        DbgPrintEx(5u, 1u, "WERKERNELHOST: Full live kernel queue size exceeded\n");
      }
    }
    else
    {
      if ( a2 )
        *a2 = 1;
      DbgPrintEx(5u, 1u, "WERKERNELHOST: Full live kernel collection is disabled\n");
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000d68c  mov     [rsp-38h+arg_8], rbx
0x14000d691  mov     [rsp-38h+KeyHandle], rcx
0x14000d696  push    rbp
0x14000d697  push    rsi
0x14000d698  push    rdi
0x14000d699  push    r12
0x14000d69b  push    r13
0x14000d69d  push    r14
0x14000d69f  push    r15
0x14000d6a1  mov     rbp, rsp
0x14000d6a4  sub     rsp, 40h
0x14000d6a8  mov     rbx, rcx
0x14000d6ab  mov     [rbp+arg_10], 0
0x14000d6b2  mov     ecx, 38h ; '8'
0x14000d6b7  mov     [rbp+arg_18], 0
0x14000d6be  mov     rdi, rdx
0x14000d6c1  mov     [rbp+Handle], 0
0x14000d6c9  mov     [rbp+var_10], 0
0x14000d6d0  call    WerpAllocateMem
0x14000d6d5  mov     r14, rax
0x14000d6d8  test    rax, rax
0x14000d6db  jz      loc_14000D9CA
0x14000d6e1  mov     r15d, cs:dword_1400093C8
0x14000d6e8  lea     rax, [rbp+arg_18]
0x14000d6ec  mov     [rsp+40h+ResultLength], rax; ResultLength
0x14000d6f1  xor     r12d, r12d
0x14000d6f4  xor     r13d, r13d
0x14000d6f7  mov     [rsp+40h+Length], 36h ; '6'; Length
0x14000d6ff  mov     r9, r14; KeyInformation
0x14000d702  xor     r8d, r8d; KeyInformationClass
0x14000d705  xor     edx, edx; Index
0x14000d707  mov     rcx, rbx; KeyHandle
0x14000d70a  call    cs:__imp_ZwEnumerateKey
0x14000d711  nop     dword ptr [rax+rax+00h]
0x14000d716  lea     ebx, [r12+1]
0x14000d71b  jmp     loc_14000D8CF
0x14000d720  test    eax, eax
0x14000d722  jns     short loc_14000D746
0x14000d724  mov     r9d, eax
0x14000d727  lea     r8, aWerkernelhostW_24; "WERKERNELHOST: WerpCheckSpaceAvailableF"...
0x14000d72e  mov     edx, ebx; Level
0x14000d730  mov     ecx, 5; ComponentId
0x14000d735  call    cs:__imp_DbgPrintEx
0x14000d73c  nop     dword ptr [rax+rax+00h]
0x14000d741  jmp     loc_14000D8A5
0x14000d746  lea     eax, [r12+1]
0x14000d74b  cmp     eax, r12d
0x14000d74e  jb      loc_14000D932
0x14000d754  mov     ecx, [r14+0Ch]
0x14000d758  lea     r9, [rbp+Handle]
0x14000d75c  shr     rcx, 1
0x14000d75f  lea     rdx, [r14+10h]
0x14000d763  mov     r12d, eax
0x14000d766  mov     [rbp+var_C], eax
0x14000d769  xor     eax, eax
0x14000d76b  mov     r8d, 20019h
0x14000d771  mov     [r14+rcx*2+10h], ax
0x14000d777  mov     rcx, [rbp+KeyHandle]
0x14000d77b  call    WerpGetRegistryKey
0x14000d780  test    eax, eax
0x14000d782  jns     short loc_14000D7C8
0x14000d784  lea     r9, [r14+10h]
0x14000d788  mov     edx, ebx; Level
0x14000d78a  lea     r8, aWerkernelhostW_0; "WERKERNELHOST: WerpCheckSpaceAvailableF"...
0x14000d791  mov     ecx, 5; ComponentId
0x14000d796  call    cs:__imp_DbgPrintEx
0x14000d79d  nop     dword ptr [rax+rax+00h]
0x14000d7a2  mov     rcx, [rbp+Handle]; Handle
0x14000d7a6  test    rcx, rcx
0x14000d7a9  jz      loc_14000D8A5
0x14000d7af  call    cs:__imp_ZwClose
0x14000d7b6  nop     dword ptr [rax+rax+00h]
0x14000d7bb  mov     [rbp+Handle], 0
0x14000d7c3  jmp     loc_14000D8A5
0x14000d7c8  mov     rcx, [rbp+Handle]; KeyHandle
0x14000d7cc  lea     rax, [rbp+arg_10]
0x14000d7d0  xor     r9d, r9d; Length
0x14000d7d3  mov     qword ptr [rsp+40h+Length], rax; ResultLength
0x14000d7d8  xor     r8d, r8d; KeyInformation
0x14000d7db  lea     r12d, [r9+2]
0x14000d7df  mov     edx, r12d; KeyInformationClass
0x14000d7e2  call    cs:__imp_ZwQueryKey
0x14000d7e9  nop     dword ptr [rax+rax+00h]
0x14000d7ee  cmp     eax, 80000005h
0x14000d7f3  jz      short loc_14000D800
0x14000d7f5  cmp     eax, 0C0000023h
0x14000d7fa  jnz     loc_14000D8DC
0x14000d800  mov     ecx, [rbp+arg_10]
0x14000d803  call    WerpAllocateMem
0x14000d808  mov     rsi, rax
0x14000d80b  test    rax, rax
0x14000d80e  jz      loc_14000D8FB
0x14000d814  mov     r9d, [rbp+arg_10]; Length
0x14000d818  lea     rax, [rbp+arg_10]
0x14000d81c  mov     rcx, [rbp+Handle]; KeyHandle
0x14000d820  mov     r8, rsi; KeyInformation
0x14000d823  mov     edx, r12d; KeyInformationClass
0x14000d826  mov     qword ptr [rsp+40h+Length], rax; ResultLength
0x14000d82b  call    cs:__imp_ZwQueryKey
0x14000d832  nop     dword ptr [rax+rax+00h]
0x14000d837  mov     r12d, eax
0x14000d83a  test    eax, eax
0x14000d83c  js      short loc_14000D844
0x14000d83e  add     r13d, [rsi+14h]
0x14000d842  jmp     short loc_14000D861
0x14000d844  mov     r9d, r12d
0x14000d847  lea     r8, aWerkernelhostZ_2; "WERKERNELHOST: ZwQueryKey failed with 0"...
0x14000d84e  mov     edx, ebx; Level
0x14000d850  mov     ecx, 5; ComponentId
0x14000d855  call    cs:__imp_DbgPrintEx
0x14000d85c  nop     dword ptr [rax+rax+00h]
0x14000d861  mov     rcx, [rbp+Handle]; Handle
0x14000d865  test    rcx, rcx
0x14000d868  jz      short loc_14000D87E
0x14000d86a  call    cs:__imp_ZwClose
0x14000d871  nop     dword ptr [rax+rax+00h]
0x14000d876  mov     [rbp+Handle], 0
0x14000d87e  xor     edx, edx; Tag
0x14000d880  mov     rcx, rsi; P
0x14000d883  call    cs:__imp_ExFreePoolWithTag
0x14000d88a  nop     dword ptr [rax+rax+00h]
0x14000d88f  test    r12d, r12d
0x14000d892  js      loc_14000D932
0x14000d898  cmp     r13d, r15d
0x14000d89b  ja      loc_14000D932
0x14000d8a1  mov     r12d, [rbp+var_C]
0x14000d8a5  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000d8a9  lea     rax, [rbp+arg_18]
0x14000d8ad  mov     [rsp+40h+ResultLength], rax; ResultLength
0x14000d8b2  mov     r9, r14; KeyInformation
0x14000d8b5  xor     r8d, r8d; KeyInformationClass
0x14000d8b8  mov     [rsp+40h+Length], 36h ; '6'; Length
0x14000d8c0  mov     edx, r12d; Index
0x14000d8c3  call    cs:__imp_ZwEnumerateKey
0x14000d8ca  nop     dword ptr [rax+rax+00h]
0x14000d8cf  cmp     eax, 8000001Ah
0x14000d8d4  jnz     loc_14000D720
0x14000d8da  jmp     short loc_14000D932
0x14000d8dc  mov     r9d, eax
0x14000d8df  lea     r8, aWerkernelhostW_52; "WERKERNELHOST: WerpCheckSpaceAvailableF"...
0x14000d8e6  mov     edx, ebx; Level
0x14000d8e8  mov     ecx, 5; ComponentId
0x14000d8ed  call    cs:__imp_DbgPrintEx
0x14000d8f4  nop     dword ptr [rax+rax+00h]
0x14000d8f9  jmp     short loc_14000D932
0x14000d8fb  lea     r8, aWerkernelhostW_9; "WERKERNELHOST: WerpCheckSpaceAvailableF"...
0x14000d902  mov     edx, ebx; Level
0x14000d904  mov     ecx, 5; ComponentId
0x14000d909  call    cs:__imp_DbgPrintEx
0x14000d910  nop     dword ptr [rax+rax+00h]
0x14000d915  mov     rcx, [rbp+Handle]; Handle
0x14000d919  test    rcx, rcx
0x14000d91c  jz      short loc_14000D932
0x14000d91e  call    cs:__imp_ZwClose
0x14000d925  nop     dword ptr [rax+rax+00h]
0x14000d92a  mov     [rbp+Handle], 0
0x14000d932  lea     rcx, [rbp+var_10]
0x14000d936  call    WerpCountFullDump
0x14000d93b  test    eax, eax
0x14000d93d  jns     short loc_14000D95C
0x14000d93f  mov     r9d, eax
0x14000d942  lea     r8, aWerkernelhostW_27; "WERKERNELHOST: WerpCountFullDump failed"...
0x14000d949  mov     edx, ebx; Level
0x14000d94b  mov     ecx, 5; ComponentId
0x14000d950  call    cs:__imp_DbgPrintEx
0x14000d957  nop     dword ptr [rax+rax+00h]
0x14000d95c  xor     edx, edx; Tag
0x14000d95e  mov     rcx, r14; P
0x14000d961  call    cs:__imp_ExFreePoolWithTag
0x14000d968  nop     dword ptr [rax+rax+00h]
0x14000d96d  test    r15d, r15d
0x14000d970  jnz     short loc_14000D982
0x14000d972  test    rdi, rdi
0x14000d975  jz      short loc_14000D979
0x14000d977  mov     [rdi], ebx
0x14000d979  lea     r8, aWerkernelhostF_1; "WERKERNELHOST: Full live kernel collect"...
0x14000d980  jmp     short loc_14000D9B3
0x14000d982  cmp     r13d, r15d
0x14000d985  jbe     short loc_14000D99B
0x14000d987  test    rdi, rdi
0x14000d98a  jz      short loc_14000D992
0x14000d98c  mov     dword ptr [rdi], 20h ; ' '
0x14000d992  lea     r8, aWerkernelhostF_4; "WERKERNELHOST: Full live kernel queue s"...
0x14000d999  jmp     short loc_14000D9B3
0x14000d99b  cmp     [rbp+var_10], r15d
0x14000d99f  jb      short loc_14000D9C8
0x14000d9a1  test    rdi, rdi
0x14000d9a4  jz      short loc_14000D9AC
0x14000d9a6  mov     dword ptr [rdi], 21h ; '!'
0x14000d9ac  lea     r8, aWerkernelhostF_2; "WERKERNELHOST: Full live kernel dump co"...
0x14000d9b3  mov     edx, ebx; Level
0x14000d9b5  mov     ecx, 5; ComponentId
0x14000d9ba  call    cs:__imp_DbgPrintEx
0x14000d9c1  nop     dword ptr [rax+rax+00h]
0x14000d9c6  xor     ebx, ebx
0x14000d9c8  mov     eax, ebx
0x14000d9ca  mov     rbx, [rsp+40h+arg_8]
0x14000d9d2  add     rsp, 40h
0x14000d9d6  pop     r15
0x14000d9d8  pop     r14
0x14000d9da  pop     r13
0x14000d9dc  pop     r12
0x14000d9de  pop     rdi
0x14000d9df  pop     rsi
0x14000d9e0  pop     rbp
0x14000d9e1  retn
```
