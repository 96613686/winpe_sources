# VhdmpiVhd2SetParentLocator(_VHD2_BACKING_STORE *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_GUID const *,_GUID const *)

- ea: `0x1400e50c8`
- end: `0x1400e5383`
- name: `?VhdmpiVhd2SetParentLocator@@YAJPEAU_VHD2_BACKING_STORE@@PEAU_UNICODE_STRING@@11PEBU_GUID@@2@Z`
- size: `699`
- prototype: `int(struct _VHD2_BACKING_STORE *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400c53f0`

## callees

- `0x1400189c0`
- `0x14001bc1c`
- `0x14001c088`
- `0x140040de4`
- `0x14005e100`
- `0x14009db68`
- `0x1400d7204`
- `0x1400e50c8`

## import_xrefs

- `ntoskrnl!RtlStringFromGUID` at `0x1400e51a0`
- `ntoskrnl!RtlStringFromGUID` at `0x1400e52f7`
- `ntoskrnl!RtlStringFromGUID` at `0x1400e51a0`
- `ntoskrnl!RtlStringFromGUID` at `0x1400e52f7`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400e51e9`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400e5245`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400e52a1`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400e51e9`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400e5245`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400e52a1`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e5188`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e51cc`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e5228`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e5284`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e52dc`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e5188`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e51cc`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e5228`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e5284`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e52dc`
- `ntoskrnl!ExAllocatePool2` at `0x1400e5128`
- `ntoskrnl!ExAllocatePool2` at `0x1400e5128`

## string_xrefs

- `0x1400e5177`: `parent_linkage`
- `0x1400e52c3`: `parent_linkage2`
- `0x1400e526b`: `volume_path`
- `0x1400e51bd`: `absolute_win32_path`
- `0x1400e5210`: `relative_path`

## pseudocode

```c
__int64 __fastcall VhdmpiVhd2SetParentLocator(
        KSPIN_LOCK *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        const struct _GUID *Guid,
        const struct _GUID *a6)
{
  struct _UNICODE_STRING *Pool2; // rax
  struct _UNICODE_STRING *v11; // rsi
  NTSTATUS v12; // ebx
  unsigned __int16 v14; // di
  __int64 v15; // rbx
  struct _UNICODE_STRING *v16; // rbx
  __int64 v17; // rbx
  struct _UNICODE_STRING *v18; // rbx
  struct _UNICODE_STRING *v19; // rsi
  __int128 v20; // xmm1
  __int128 v21; // [rsp+20h] [rbp-59h] BYREF
  __int128 v22; // [rsp+30h] [rbp-49h]
  _OWORD v23[3]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v24; // [rsp+70h] [rbp-9h]

  memset(v23, 0, sizeof(v23));
  v24 = 0;
  *(_QWORD *)((char *)&v22 + 2) = 0;
  v21 = VHD2_PARENT_LOCATOR_VHD2_TYPE;
  LOWORD(v22) = 0;
  Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(256, 160, 1836266070);
  *((_QWORD *)&v22 + 1) = Pool2;
  v11 = Pool2;
  if ( !Pool2 )
    goto LABEL_2;
  memset(Pool2, 0, 0xA0u);
  LOWORD(v22) = 1;
  v14 = 1;
  if ( !RtlCreateUnicodeString(v11, L"parent_linkage") )
    goto LABEL_2;
  v12 = RtlStringFromGUID(Guid, v11 + 1);
  if ( v12 < 0 )
    goto LABEL_3;
  if ( a2->Length )
  {
    v14 = 2;
    LOWORD(v22) = 2;
    if ( !RtlCreateUnicodeString(v11 + 2, L"absolute_win32_path") )
      goto LABEL_2;
    v12 = RtlDuplicateUnicodeString(0, a2, v11 + 3);
    if ( v12 < 0 )
      goto LABEL_3;
  }
  if ( a3->Length )
  {
    v15 = 2LL * v14++;
    v16 = &v11[v15];
    LOWORD(v22) = v14;
    if ( !RtlCreateUnicodeString(v16, L"relative_path") )
      goto LABEL_2;
    v12 = RtlDuplicateUnicodeString(0, a3, v16 + 1);
    if ( v12 < 0 )
      goto LABEL_3;
  }
  if ( a4->Length )
  {
    v17 = 2LL * v14++;
    v18 = &v11[v17];
    LOWORD(v22) = v14;
    if ( !RtlCreateUnicodeString(v18, L"volume_path") )
      goto LABEL_2;
    v12 = RtlDuplicateUnicodeString(0, a4, v18 + 1);
    if ( v12 < 0 )
      goto LABEL_3;
  }
  if ( a6 )
  {
    v19 = &v11[2 * v14];
    LOWORD(v22) = v14 + 1;
    if ( RtlCreateUnicodeString(v19, L"parent_linkage2") )
    {
      v12 = RtlStringFromGUID(a6, v19 + 1);
      if ( v12 < 0 )
        goto LABEL_3;
      goto LABEL_19;
    }
LABEL_2:
    v12 = -1073741670;
    goto LABEL_3;
  }
LABEL_19:
  VhdmpiAeInitializeSynchronousCompletion(v23);
  v12 = Vhd2SetParentLocator(a1 + 280);
  if ( v12 == 259 )
    v12 = VhdmpiAeWaitForSynchronousCompletion(v23);
  if ( v12 >= 0 )
  {
    VhdmpiAcquirePassiveLock(a1 + 666);
    Vhd2UninitializeParentLocator(a1 + 668);
    v20 = v22;
    *((_OWORD *)a1 + 334) = v21;
    *((_OWORD *)a1 + 335) = v20;
    VhdmpiReleasePassiveLock(a1 + 666);
    return 0;
  }
LABEL_3:
  Vhd2UninitializeParentLocator(&v21);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400e50c8  push    rbp
0x1400e50ca  push    rbx
0x1400e50cb  push    rsi
0x1400e50cc  push    rdi
0x1400e50cd  push    r12
0x1400e50cf  push    r13
0x1400e50d1  push    r14
0x1400e50d3  push    r15
0x1400e50d5  lea     rbp, [rsp-0Fh]
0x1400e50da  sub     rsp, 88h
0x1400e50e1  xorps   xmm0, xmm0
0x1400e50e4  mov     edi, 0A0h
0x1400e50e9  movups  [rbp+47h+var_80], xmm0
0x1400e50ed  mov     r12, r8
0x1400e50f0  mov     r15, rdx
0x1400e50f3  movups  [rbp+47h+var_70], xmm0
0x1400e50f7  mov     r14, rcx
0x1400e50fa  xor     eax, eax
0x1400e50fc  movups  [rbp+47h+var_60], xmm0
0x1400e5100  xor     ebx, ebx
0x1400e5102  mov     r8d, 6D733256h
0x1400e5108  movups  xmm0, cs:VHD2_PARENT_LOCATOR_VHD2_TYPE
0x1400e510f  mov     edx, edi
0x1400e5111  mov     [rbp+47h+var_50], rax
0x1400e5115  lea     ecx, [rdi+60h]
0x1400e5118  mov     qword ptr [rbp+47h+var_90+2], rbx
0x1400e511c  movdqu  [rbp+47h+var_A0], xmm0
0x1400e5121  mov     r13, r9
0x1400e5124  mov     word ptr [rbp+47h+var_90], bx
0x1400e5128  call    cs:__imp_ExAllocatePool2
0x1400e512f  nop     dword ptr [rax+rax+00h]
0x1400e5134  mov     qword ptr [rbp+47h+var_90+8], rax
0x1400e5138  mov     rsi, rax
0x1400e513b  test    rax, rax
0x1400e513e  jnz     short loc_1400E5165
0x1400e5140  mov     ebx, 0C000009Ah
0x1400e5145  lea     rcx, [rbp+47h+var_A0]
0x1400e5149  call    Vhd2UninitializeParentLocator
0x1400e514e  mov     eax, ebx
0x1400e5150  add     rsp, 88h
0x1400e5157  pop     r15
0x1400e5159  pop     r14
0x1400e515b  pop     r13
0x1400e515d  pop     r12
0x1400e515f  pop     rdi
0x1400e5160  pop     rsi
0x1400e5161  pop     rbx
0x1400e5162  pop     rbp
0x1400e5163  retn
0x1400e5165  mov     r8, rdi; Size
0x1400e5168  xor     edx, edx; Val
0x1400e516a  mov     rcx, rsi; void *
0x1400e516d  call    memset
0x1400e5172  mov     eax, 1
0x1400e5177  lea     rdx, aParentLinkage; "parent_linkage"
0x1400e517e  mov     rcx, rsi; DestinationString
0x1400e5181  mov     word ptr [rbp+47h+var_90], ax
0x1400e5185  movzx   edi, ax
0x1400e5188  call    cs:__imp_RtlCreateUnicodeString
0x1400e518f  nop     dword ptr [rax+rax+00h]
0x1400e5194  test    al, al
0x1400e5196  jz      short loc_1400E5140
0x1400e5198  mov     rcx, [rbp+47h+Guid]; Guid
0x1400e519c  lea     rdx, [rsi+10h]; GuidString
0x1400e51a0  call    cs:__imp_RtlStringFromGUID
0x1400e51a7  nop     dword ptr [rax+rax+00h]
0x1400e51ac  mov     ebx, eax
0x1400e51ae  xor     eax, eax
0x1400e51b0  test    ebx, ebx
0x1400e51b2  js      short loc_1400E5145
0x1400e51b4  cmp     [r15], ax
0x1400e51b8  jbe     short loc_1400E5203
0x1400e51ba  lea     edi, [rax+2]
0x1400e51bd  lea     rdx, aAbsoluteWin32P; "absolute_win32_path"
0x1400e51c4  mov     word ptr [rbp+47h+var_90], di
0x1400e51c8  lea     rcx, [rsi+20h]; DestinationString
0x1400e51cc  call    cs:__imp_RtlCreateUnicodeString
0x1400e51d3  nop     dword ptr [rax+rax+00h]
0x1400e51d8  test    al, al
0x1400e51da  jz      loc_1400E5140
0x1400e51e0  lea     r8, [rsi+30h]; StringOut
0x1400e51e4  mov     rdx, r15; StringIn
0x1400e51e7  xor     ecx, ecx; Flags
0x1400e51e9  call    cs:__imp_RtlDuplicateUnicodeString
0x1400e51f0  nop     dword ptr [rax+rax+00h]
0x1400e51f5  xor     r15d, r15d
0x1400e51f8  mov     ebx, eax
0x1400e51fa  test    eax, eax
0x1400e51fc  jns     short loc_1400E5206
0x1400e51fe  jmp     loc_1400E5145
0x1400e5203  xor     r15d, r15d
0x1400e5206  cmp     [r12], r15w
0x1400e520b  jbe     short loc_1400E525B
0x1400e520d  movzx   ebx, di
0x1400e5210  lea     rdx, aRelativePath; "relative_path"
0x1400e5217  shl     rbx, 5
0x1400e521b  inc     di
0x1400e521e  add     rbx, rsi
0x1400e5221  mov     word ptr [rbp+47h+var_90], di
0x1400e5225  mov     rcx, rbx; DestinationString
0x1400e5228  call    cs:__imp_RtlCreateUnicodeString
0x1400e522f  nop     dword ptr [rax+rax+00h]
0x1400e5234  test    al, al
0x1400e5236  jz      loc_1400E5140
0x1400e523c  lea     r8, [rbx+10h]; StringOut
0x1400e5240  mov     rdx, r12; StringIn
0x1400e5243  xor     ecx, ecx; Flags
0x1400e5245  call    cs:__imp_RtlDuplicateUnicodeString
0x1400e524c  nop     dword ptr [rax+rax+00h]
0x1400e5251  mov     ebx, eax
0x1400e5253  test    eax, eax
0x1400e5255  js      loc_1400E5145
0x1400e525b  mov     r12d, 1
0x1400e5261  cmp     [r13+0], r15w
0x1400e5266  jbe     short loc_1400E52B7
0x1400e5268  movzx   ebx, di
0x1400e526b  lea     rdx, aVolumePath; "volume_path"
0x1400e5272  shl     rbx, 5
0x1400e5276  add     di, r12w
0x1400e527a  add     rbx, rsi
0x1400e527d  mov     word ptr [rbp+47h+var_90], di
0x1400e5281  mov     rcx, rbx; DestinationString
0x1400e5284  call    cs:__imp_RtlCreateUnicodeString
0x1400e528b  nop     dword ptr [rax+rax+00h]
0x1400e5290  test    al, al
0x1400e5292  jz      loc_1400E5140
0x1400e5298  lea     r8, [rbx+10h]; StringOut
0x1400e529c  mov     rdx, r13; StringIn
0x1400e529f  xor     ecx, ecx; Flags
0x1400e52a1  call    cs:__imp_RtlDuplicateUnicodeString
0x1400e52a8  nop     dword ptr [rax+rax+00h]
0x1400e52ad  mov     ebx, eax
0x1400e52af  test    eax, eax
0x1400e52b1  js      loc_1400E5145
0x1400e52b7  mov     rbx, [rbp+47h+arg_28]
0x1400e52bb  test    rbx, rbx
0x1400e52be  jz      short loc_1400E530D
0x1400e52c0  movzx   eax, di
0x1400e52c3  lea     rdx, aParentLinkage2; "parent_linkage2"
0x1400e52ca  shl     rax, 5
0x1400e52ce  add     di, r12w
0x1400e52d2  add     rsi, rax
0x1400e52d5  mov     word ptr [rbp+47h+var_90], di
0x1400e52d9  mov     rcx, rsi; DestinationString
0x1400e52dc  call    cs:__imp_RtlCreateUnicodeString
0x1400e52e3  nop     dword ptr [rax+rax+00h]
0x1400e52e8  test    al, al
0x1400e52ea  jz      loc_1400E5140
0x1400e52f0  lea     rdx, [rsi+10h]; GuidString
0x1400e52f4  mov     rcx, rbx; Guid
0x1400e52f7  call    cs:__imp_RtlStringFromGUID
0x1400e52fe  nop     dword ptr [rax+rax+00h]
0x1400e5303  mov     ebx, eax
0x1400e5305  test    eax, eax
0x1400e5307  js      loc_1400E5145
0x1400e530d  lea     rcx, [rbp+47h+var_80]
0x1400e5311  call    VhdmpiAeInitializeSynchronousCompletion
0x1400e5316  lea     rcx, [r14+8C0h]; SpinLock
0x1400e531d  lea     r8, [rbp+47h+var_80]
0x1400e5321  lea     rdx, [rbp+47h+var_A0]
0x1400e5325  call    Vhd2SetParentLocator
0x1400e532a  mov     ebx, eax
0x1400e532c  cmp     eax, 103h
0x1400e5331  jnz     short loc_1400E533E
0x1400e5333  lea     rcx, [rbp+47h+var_80]
0x1400e5337  call    VhdmpiAeWaitForSynchronousCompletion
0x1400e533c  mov     ebx, eax
0x1400e533e  test    ebx, ebx
0x1400e5340  js      loc_1400E5145
0x1400e5346  lea     rdi, [r14+14D0h]
0x1400e534d  mov     rcx, rdi
0x1400e5350  call    VhdmpiAcquirePassiveLock
0x1400e5355  lea     rbx, [r14+14E0h]
0x1400e535c  mov     rcx, rbx
0x1400e535f  call    Vhd2UninitializeParentLocator
0x1400e5364  movups  xmm0, [rbp+47h+var_A0]
0x1400e5368  mov     rcx, rdi
0x1400e536b  movups  xmm1, [rbp+47h+var_90]
0x1400e536f  movups  xmmword ptr [rbx], xmm0
0x1400e5372  movups  xmmword ptr [rbx+10h], xmm1
0x1400e5376  call    VhdmpiReleasePassiveLock
0x1400e537b  mov     ebx, r15d
0x1400e537e  jmp     loc_1400E514E
```
