# VhdmpiVhd2SetParentLocator(_VHD2_BACKING_STORE *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_GUID const *,_GUID const *)

- ea: `0x1400e5138`
- end: `0x1400e53f3`
- name: `?VhdmpiVhd2SetParentLocator@@YAJPEAU_VHD2_BACKING_STORE@@PEAU_UNICODE_STRING@@11PEBU_GUID@@2@Z`
- size: `699`
- prototype: `int(struct _VHD2_BACKING_STORE *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400c5400`

## callees

- `0x140018520`
- `0x14001b7fc`
- `0x14001bc68`
- `0x1400409f4`
- `0x14005dd00`
- `0x14009db68`
- `0x1400d7274`
- `0x1400e5138`

## import_xrefs

- `ntoskrnl!RtlStringFromGUID` at `0x1400e5210`
- `ntoskrnl!RtlStringFromGUID` at `0x1400e5367`
- `ntoskrnl!RtlStringFromGUID` at `0x1400e5210`
- `ntoskrnl!RtlStringFromGUID` at `0x1400e5367`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400e5259`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400e52b5`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400e5311`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400e5259`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400e52b5`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400e5311`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e51f8`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e523c`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e5298`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e52f4`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e534c`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e51f8`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e523c`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e5298`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e52f4`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1400e534c`
- `ntoskrnl!ExAllocatePool2` at `0x1400e5198`
- `ntoskrnl!ExAllocatePool2` at `0x1400e5198`

## string_xrefs

- `0x1400e51e7`: `parent_linkage`
- `0x1400e5333`: `parent_linkage2`
- `0x1400e522d`: `absolute_win32_path`
- `0x1400e5280`: `relative_path`
- `0x1400e52db`: `volume_path`

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
  __int64 v20; // rdx
  __int64 v21; // r8
  __int128 v22; // xmm1
  __int128 v23; // [rsp+20h] [rbp-59h] BYREF
  __int128 v24; // [rsp+30h] [rbp-49h]
  _OWORD v25[3]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v26; // [rsp+70h] [rbp-9h]

  memset(v25, 0, sizeof(v25));
  v26 = 0;
  *(_QWORD *)((char *)&v24 + 2) = 0;
  v23 = VHD2_PARENT_LOCATOR_VHD2_TYPE;
  LOWORD(v24) = 0;
  Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(256, 160, 1836266070);
  *((_QWORD *)&v24 + 1) = Pool2;
  v11 = Pool2;
  if ( !Pool2 )
    goto LABEL_2;
  memset(Pool2, 0, 0xA0u);
  LOWORD(v24) = 1;
  v14 = 1;
  if ( !RtlCreateUnicodeString(v11, L"parent_linkage") )
    goto LABEL_2;
  v12 = RtlStringFromGUID(Guid, v11 + 1);
  if ( v12 < 0 )
    goto LABEL_3;
  if ( a2->Length )
  {
    v14 = 2;
    LOWORD(v24) = 2;
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
    LOWORD(v24) = v14;
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
    LOWORD(v24) = v14;
    if ( !RtlCreateUnicodeString(v18, L"volume_path") )
      goto LABEL_2;
    v12 = RtlDuplicateUnicodeString(0, a4, v18 + 1);
    if ( v12 < 0 )
      goto LABEL_3;
  }
  if ( a6 )
  {
    v19 = &v11[2 * v14];
    LOWORD(v24) = v14 + 1;
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
  VhdmpiAeInitializeSynchronousCompletion(v25);
  v12 = Vhd2SetParentLocator(a1 + 280);
  if ( v12 == 259 )
    v12 = VhdmpiAeWaitForSynchronousCompletion(v25);
  if ( v12 >= 0 )
  {
    VhdmpiAcquirePassiveLock(a1 + 666, v20, v21);
    Vhd2UninitializeParentLocator(a1 + 668);
    v22 = v24;
    *((_OWORD *)a1 + 334) = v23;
    *((_OWORD *)a1 + 335) = v22;
    VhdmpiReleasePassiveLock(a1 + 666);
    return 0;
  }
LABEL_3:
  Vhd2UninitializeParentLocator(&v23);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400e5138  push    rbp
0x1400e513a  push    rbx
0x1400e513b  push    rsi
0x1400e513c  push    rdi
0x1400e513d  push    r12
0x1400e513f  push    r13
0x1400e5141  push    r14
0x1400e5143  push    r15
0x1400e5145  lea     rbp, [rsp-0Fh]
0x1400e514a  sub     rsp, 88h
0x1400e5151  xorps   xmm0, xmm0
0x1400e5154  mov     edi, 0A0h
0x1400e5159  movups  [rbp+47h+var_80], xmm0
0x1400e515d  mov     r12, r8
0x1400e5160  mov     r15, rdx
0x1400e5163  movups  [rbp+47h+var_70], xmm0
0x1400e5167  mov     r14, rcx
0x1400e516a  xor     eax, eax
0x1400e516c  movups  [rbp+47h+var_60], xmm0
0x1400e5170  xor     ebx, ebx
0x1400e5172  mov     r8d, 6D733256h
0x1400e5178  movups  xmm0, cs:VHD2_PARENT_LOCATOR_VHD2_TYPE
0x1400e517f  mov     edx, edi
0x1400e5181  mov     [rbp+47h+var_50], rax
0x1400e5185  lea     ecx, [rdi+60h]
0x1400e5188  mov     qword ptr [rbp+47h+var_90+2], rbx
0x1400e518c  movdqu  [rbp+47h+var_A0], xmm0
0x1400e5191  mov     r13, r9
0x1400e5194  mov     word ptr [rbp+47h+var_90], bx
0x1400e5198  call    cs:__imp_ExAllocatePool2
0x1400e519f  nop     dword ptr [rax+rax+00h]
0x1400e51a4  mov     qword ptr [rbp+47h+var_90+8], rax
0x1400e51a8  mov     rsi, rax
0x1400e51ab  test    rax, rax
0x1400e51ae  jnz     short loc_1400E51D5
0x1400e51b0  mov     ebx, 0C000009Ah
0x1400e51b5  lea     rcx, [rbp+47h+var_A0]
0x1400e51b9  call    Vhd2UninitializeParentLocator
0x1400e51be  mov     eax, ebx
0x1400e51c0  add     rsp, 88h
0x1400e51c7  pop     r15
0x1400e51c9  pop     r14
0x1400e51cb  pop     r13
0x1400e51cd  pop     r12
0x1400e51cf  pop     rdi
0x1400e51d0  pop     rsi
0x1400e51d1  pop     rbx
0x1400e51d2  pop     rbp
0x1400e51d3  retn
0x1400e51d5  mov     r8, rdi; Size
0x1400e51d8  xor     edx, edx; Val
0x1400e51da  mov     rcx, rsi; void *
0x1400e51dd  call    memset
0x1400e51e2  mov     eax, 1
0x1400e51e7  lea     rdx, aParentLinkage; "parent_linkage"
0x1400e51ee  mov     rcx, rsi; DestinationString
0x1400e51f1  mov     word ptr [rbp+47h+var_90], ax
0x1400e51f5  movzx   edi, ax
0x1400e51f8  call    cs:__imp_RtlCreateUnicodeString
0x1400e51ff  nop     dword ptr [rax+rax+00h]
0x1400e5204  test    al, al
0x1400e5206  jz      short loc_1400E51B0
0x1400e5208  mov     rcx, [rbp+47h+Guid]; Guid
0x1400e520c  lea     rdx, [rsi+10h]; GuidString
0x1400e5210  call    cs:__imp_RtlStringFromGUID
0x1400e5217  nop     dword ptr [rax+rax+00h]
0x1400e521c  mov     ebx, eax
0x1400e521e  xor     eax, eax
0x1400e5220  test    ebx, ebx
0x1400e5222  js      short loc_1400E51B5
0x1400e5224  cmp     [r15], ax
0x1400e5228  jbe     short loc_1400E5273
0x1400e522a  lea     edi, [rax+2]
0x1400e522d  lea     rdx, aAbsoluteWin32P; "absolute_win32_path"
0x1400e5234  mov     word ptr [rbp+47h+var_90], di
0x1400e5238  lea     rcx, [rsi+20h]; DestinationString
0x1400e523c  call    cs:__imp_RtlCreateUnicodeString
0x1400e5243  nop     dword ptr [rax+rax+00h]
0x1400e5248  test    al, al
0x1400e524a  jz      loc_1400E51B0
0x1400e5250  lea     r8, [rsi+30h]; StringOut
0x1400e5254  mov     rdx, r15; StringIn
0x1400e5257  xor     ecx, ecx; Flags
0x1400e5259  call    cs:__imp_RtlDuplicateUnicodeString
0x1400e5260  nop     dword ptr [rax+rax+00h]
0x1400e5265  xor     r15d, r15d
0x1400e5268  mov     ebx, eax
0x1400e526a  test    eax, eax
0x1400e526c  jns     short loc_1400E5276
0x1400e526e  jmp     loc_1400E51B5
0x1400e5273  xor     r15d, r15d
0x1400e5276  cmp     [r12], r15w
0x1400e527b  jbe     short loc_1400E52CB
0x1400e527d  movzx   ebx, di
0x1400e5280  lea     rdx, aRelativePath; "relative_path"
0x1400e5287  shl     rbx, 5
0x1400e528b  inc     di
0x1400e528e  add     rbx, rsi
0x1400e5291  mov     word ptr [rbp+47h+var_90], di
0x1400e5295  mov     rcx, rbx; DestinationString
0x1400e5298  call    cs:__imp_RtlCreateUnicodeString
0x1400e529f  nop     dword ptr [rax+rax+00h]
0x1400e52a4  test    al, al
0x1400e52a6  jz      loc_1400E51B0
0x1400e52ac  lea     r8, [rbx+10h]; StringOut
0x1400e52b0  mov     rdx, r12; StringIn
0x1400e52b3  xor     ecx, ecx; Flags
0x1400e52b5  call    cs:__imp_RtlDuplicateUnicodeString
0x1400e52bc  nop     dword ptr [rax+rax+00h]
0x1400e52c1  mov     ebx, eax
0x1400e52c3  test    eax, eax
0x1400e52c5  js      loc_1400E51B5
0x1400e52cb  mov     r12d, 1
0x1400e52d1  cmp     [r13+0], r15w
0x1400e52d6  jbe     short loc_1400E5327
0x1400e52d8  movzx   ebx, di
0x1400e52db  lea     rdx, aVolumePath; "volume_path"
0x1400e52e2  shl     rbx, 5
0x1400e52e6  add     di, r12w
0x1400e52ea  add     rbx, rsi
0x1400e52ed  mov     word ptr [rbp+47h+var_90], di
0x1400e52f1  mov     rcx, rbx; DestinationString
0x1400e52f4  call    cs:__imp_RtlCreateUnicodeString
0x1400e52fb  nop     dword ptr [rax+rax+00h]
0x1400e5300  test    al, al
0x1400e5302  jz      loc_1400E51B0
0x1400e5308  lea     r8, [rbx+10h]; StringOut
0x1400e530c  mov     rdx, r13; StringIn
0x1400e530f  xor     ecx, ecx; Flags
0x1400e5311  call    cs:__imp_RtlDuplicateUnicodeString
0x1400e5318  nop     dword ptr [rax+rax+00h]
0x1400e531d  mov     ebx, eax
0x1400e531f  test    eax, eax
0x1400e5321  js      loc_1400E51B5
0x1400e5327  mov     rbx, [rbp+47h+arg_28]
0x1400e532b  test    rbx, rbx
0x1400e532e  jz      short loc_1400E537D
0x1400e5330  movzx   eax, di
0x1400e5333  lea     rdx, aParentLinkage2; "parent_linkage2"
0x1400e533a  shl     rax, 5
0x1400e533e  add     di, r12w
0x1400e5342  add     rsi, rax
0x1400e5345  mov     word ptr [rbp+47h+var_90], di
0x1400e5349  mov     rcx, rsi; DestinationString
0x1400e534c  call    cs:__imp_RtlCreateUnicodeString
0x1400e5353  nop     dword ptr [rax+rax+00h]
0x1400e5358  test    al, al
0x1400e535a  jz      loc_1400E51B0
0x1400e5360  lea     rdx, [rsi+10h]; GuidString
0x1400e5364  mov     rcx, rbx; Guid
0x1400e5367  call    cs:__imp_RtlStringFromGUID
0x1400e536e  nop     dword ptr [rax+rax+00h]
0x1400e5373  mov     ebx, eax
0x1400e5375  test    eax, eax
0x1400e5377  js      loc_1400E51B5
0x1400e537d  lea     rcx, [rbp+47h+var_80]
0x1400e5381  call    VhdmpiAeInitializeSynchronousCompletion
0x1400e5386  lea     rcx, [r14+8C0h]; SpinLock
0x1400e538d  lea     r8, [rbp+47h+var_80]
0x1400e5391  lea     rdx, [rbp+47h+var_A0]
0x1400e5395  call    Vhd2SetParentLocator
0x1400e539a  mov     ebx, eax
0x1400e539c  cmp     eax, 103h
0x1400e53a1  jnz     short loc_1400E53AE
0x1400e53a3  lea     rcx, [rbp+47h+var_80]
0x1400e53a7  call    VhdmpiAeWaitForSynchronousCompletion
0x1400e53ac  mov     ebx, eax
0x1400e53ae  test    ebx, ebx
0x1400e53b0  js      loc_1400E51B5
0x1400e53b6  lea     rdi, [r14+14D0h]
0x1400e53bd  mov     rcx, rdi
0x1400e53c0  call    VhdmpiAcquirePassiveLock
0x1400e53c5  lea     rbx, [r14+14E0h]
0x1400e53cc  mov     rcx, rbx
0x1400e53cf  call    Vhd2UninitializeParentLocator
0x1400e53d4  movups  xmm0, [rbp+47h+var_A0]
0x1400e53d8  mov     rcx, rdi
0x1400e53db  movups  xmm1, [rbp+47h+var_90]
0x1400e53df  movups  xmmword ptr [rbx], xmm0
0x1400e53e2  movups  xmmword ptr [rbx+10h], xmm1
0x1400e53e6  call    VhdmpiReleasePassiveLock
0x1400e53eb  mov     ebx, r15d
0x1400e53ee  jmp     loc_1400E51BE
```
