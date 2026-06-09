# VsmmPhuStoreMemoryBlockOpenFile

- ea: `0x1400b27dc`
- end: `0x1400b2bc2`
- name: `VsmmPhuStoreMemoryBlockOpenFile`
- size: `998`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400a078c`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x14002f524`
- `0x1400303c0`
- `0x14007579c`
- `0x1400b27dc`
- `0x1400de9ac`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400b29e9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400b29e9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b2a81`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b2a81`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400b2a47`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400b2a47`
- `ntoskrnl!IoFileObjectType` at `0x1400b29bb`
- `ntoskrnl!IoFileObjectType` at `0x1400b2a2e`

## string_xrefs

- `0x1400b2847`: `VsmmPhuStoreMemoryBlockOpenFile`
- `0x1400b2884`: `VsmmPhuStoreMemoryBlockOpenFile`
- `0x1400b28be`: `VsmmPhuStoreMemoryBlockOpenFile`
- `0x1400b2923`: `VsmmPhuStoreMemoryBlockOpenFile`
- `0x1400b2a10`: `VsmmPhuStoreMemoryBlockOpenFile`
- `0x1400b2a69`: `VsmmPhuStoreMemoryBlockOpenFile`
- `0x1400b2ace`: `VsmmPhuStoreMemoryBlockOpenFile`

## pseudocode

```c
__int64 __fastcall VsmmPhuStoreMemoryBlockOpenFile(__int64 a1, __int64 a2, ACCESS_MASK a3, void **a4)
{
  char *v4; // r14
  __int64 v8; // rax
  __int64 v9; // r15
  NTSTATUS v10; // ebx
  void **v11; // rcx
  int v12; // r8d
  void *v13; // rcx
  NTSTATUS v14; // eax
  PVOID v15; // r15
  char v17; // [rsp+40h] [rbp-C0h] BYREF
  PVOID Object; // [rsp+48h] [rbp-B8h] BYREF
  PHANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v22[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v23[16]; // [rsp+90h] [rbp-70h] BYREF
  void *p_Object; // [rsp+A0h] [rbp-60h]
  __int64 v25; // [rsp+A8h] [rbp-58h]
  void *p_Handle; // [rsp+B0h] [rbp-50h]
  __int64 v27; // [rsp+B8h] [rbp-48h]
  char *v28; // [rsp+C0h] [rbp-40h]
  __int64 v29; // [rsp+C8h] [rbp-38h]
  _DWORD *v30; // [rsp+D0h] [rbp-30h]
  __int64 v31; // [rsp+D8h] [rbp-28h]
  __int64 v32; // [rsp+E0h] [rbp-20h]
  _DWORD v33[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 *v34; // [rsp+F0h] [rbp-10h]
  __int64 v35; // [rsp+F8h] [rbp-8h]

  v4 = 0;
  Handle = a4;
  Object = 0;
  v8 = VsmmPhuStorepObjectLookup(*(_QWORD *)(a1 + 8648), 2, a2);
  v9 = v8;
  if ( !v8 )
  {
    v10 = -1073741275;
    VidTraceErrorStatusInternal0("VsmmPhuStoreMemoryBlockOpenFile", "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c", 4206);
LABEL_24:
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v22, "VsmmPhuStoreMemoryBlockOpenFile");
      tlgCreate1Sz_char(v23, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      LODWORD(Object) = 4302;
      p_Object = &Object;
      v25 = 4;
      p_Handle = &Handle;
      LODWORD(Handle) = v10;
      v28 = (char *)(a1 + 656);
      v27 = 4;
      v30 = v33;
      v32 = *(_QWORD *)(a1 + 128);
      v33[0] = *(unsigned __int16 *)(a1 + 120);
      v20 = *(_QWORD *)(a1 + 648);
      v34 = &v20;
      v29 = 16;
      v31 = 2;
      v33[1] = 0;
      v35 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004F7EB, 0, 0, 10, v21);
    }
    return (unsigned int)v10;
  }
  if ( *(_BYTE *)(v8 + 72) )
  {
    v11 = *(void ***)(v8 + 152);
  }
  else
  {
    if ( !*(_BYTE *)(a1 + 8657) )
    {
      v10 = -1073741436;
      VidTraceErrorStatusInternal0(
        "VsmmPhuStoreMemoryBlockOpenFile",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        4217);
      goto LABEL_24;
    }
    v10 = VsmmMemoryBlockLookupByPersistId(a1, a2, 0, &Object);
    if ( v10 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStoreMemoryBlockOpenFile",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        4233);
      v4 = (char *)Object;
      goto LABEL_21;
    }
    v4 = (char *)Object;
    v11 = (void **)*((_QWORD *)Object + 96);
  }
  if ( v11 )
  {
    v13 = *v11;
    Object = 0;
    v14 = ObReferenceObjectByHandle(v13, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
    v15 = Object;
    v10 = v14;
    if ( v14 >= 0 )
    {
      v10 = ObOpenObjectByPointer(Object, 0, 0, a3, (POBJECT_TYPE)IoFileObjectType, 1, Handle);
      if ( v10 >= 0 )
        v10 = 0;
      else
        VidTraceErrorStatusInternal0(
          "VsmmPhuStoreMemoryBlockOpenFile",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
          4285);
    }
    else
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStoreMemoryBlockOpenFile",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        4271);
    }
    if ( v15 )
      ObfDereferenceObject(v15);
  }
  else
  {
    v10 = -1073741436;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v22, "VsmmPhuStoreMemoryBlockOpenFile");
      tlgCreate1Sz_char(v23, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      LODWORD(Object) = v12;
      p_Object = &Handle;
      LODWORD(Handle) = 4249;
      p_Handle = &Object;
      v17 = *(_BYTE *)(v9 + 72);
      v25 = 4;
      v28 = &v17;
      v27 = 4;
      v29 = 1;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004F791, 0, 0, 7, v21);
    }
  }
LABEL_21:
  if ( v4 )
    VidOpCtrlFinish(v4 + 128);
  if ( v10 < 0 )
    goto LABEL_24;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400b27dc  push    rbp
0x1400b27de  push    rbx
0x1400b27df  push    r12
0x1400b27e1  push    r13
0x1400b27e3  push    r14
0x1400b27e5  push    r15
0x1400b27e7  lea     rbp, [rsp-18h]
0x1400b27ec  sub     rsp, 118h
0x1400b27f3  mov     rax, cs:__security_cookie
0x1400b27fa  xor     rax, rsp
0x1400b27fd  mov     [rbp+40h+var_40], rax
0x1400b2801  xor     r14d, r14d
0x1400b2804  mov     [rsp+140h+var_F0], r9
0x1400b2809  mov     r12d, r8d
0x1400b280c  mov     [rsp+140h+var_F8], r14
0x1400b2811  mov     rbx, rdx
0x1400b2814  mov     r13, rcx
0x1400b2817  mov     rcx, [rcx+21C8h]
0x1400b281e  mov     r8, rdx
0x1400b2821  lea     edx, [r14+2]
0x1400b2825  call    VsmmPhuStorepObjectLookup
0x1400b282a  mov     r15, rax
0x1400b282d  test    rax, rax
0x1400b2830  jnz     short loc_1400B2858
0x1400b2832  mov     ebx, 0C0000225h
0x1400b2837  mov     r9d, ebx
0x1400b283a  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b2841  mov     r8d, 106Eh
0x1400b2847  lea     rcx, aVsmmphustoreme_0; "VsmmPhuStoreMemoryBlockOpenFile"
0x1400b284e  call    VidTraceErrorStatusInternal0
0x1400b2853  jmp     loc_1400B2AA6
0x1400b2858  cmp     [rax+48h], r14b
0x1400b285c  jnz     loc_1400B28E2
0x1400b2862  cmp     [r13+21D1h], r14b
0x1400b2869  jnz     short loc_1400B2895
0x1400b286b  mov     r8d, 0C0000184h
0x1400b2871  mov     ebx, r8d
0x1400b2874  mov     r9d, r8d
0x1400b2877  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b287e  mov     r8d, 1079h
0x1400b2884  lea     rcx, aVsmmphustoreme_0; "VsmmPhuStoreMemoryBlockOpenFile"
0x1400b288b  call    VidTraceErrorStatusInternal0
0x1400b2890  jmp     loc_1400B2AA6
0x1400b2895  lea     r9, [rsp+140h+var_F8]
0x1400b289a  xor     r8d, r8d
0x1400b289d  mov     rdx, rbx
0x1400b28a0  mov     rcx, r13
0x1400b28a3  call    VsmmMemoryBlockLookupByPersistId
0x1400b28a8  mov     ebx, eax
0x1400b28aa  test    eax, eax
0x1400b28ac  jns     short loc_1400B28D4
0x1400b28ae  mov     r9d, eax
0x1400b28b1  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b28b8  mov     r8d, 1089h
0x1400b28be  lea     rcx, aVsmmphustoreme_0; "VsmmPhuStoreMemoryBlockOpenFile"
0x1400b28c5  call    VidTraceErrorStatusInternal0
0x1400b28ca  mov     r14, [rsp+140h+var_F8]
0x1400b28cf  jmp     loc_1400B2A8D
0x1400b28d4  mov     r14, [rsp+140h+var_F8]
0x1400b28d9  mov     rcx, [r14+300h]
0x1400b28e0  jmp     short loc_1400B28E9
0x1400b28e2  mov     rcx, [rax+98h]
0x1400b28e9  test    rcx, rcx
0x1400b28ec  jnz     loc_1400B29BB
0x1400b28f2  mov     eax, cs:dword_140064110
0x1400b28f8  mov     r8d, 0C0000184h
0x1400b28fe  mov     ebx, r8d
0x1400b2901  cmp     eax, 2
0x1400b2904  jbe     loc_1400B2A8D
0x1400b290a  mov     edx, 100h
0x1400b290f  lea     rcx, dword_140064110
0x1400b2916  call    _tlgKeywordOn
0x1400b291b  test    al, al
0x1400b291d  jz      loc_1400B2A8D
0x1400b2923  lea     rdx, aVsmmphustoreme_0; "VsmmPhuStoreMemoryBlockOpenFile"
0x1400b292a  lea     rcx, [rbp+40h+var_C0]
0x1400b292e  call    _tlgCreate1Sz_char
0x1400b2933  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b293a  lea     rcx, [rbp+40h+var_B0]
0x1400b293e  call    _tlgCreate1Sz_char
0x1400b2943  lea     rax, [rsp+140h+var_F0]
0x1400b2948  mov     dword ptr [rsp+140h+var_F8], r8d
0x1400b294d  mov     [rbp+40h+var_A0], rax
0x1400b2951  lea     rdx, byte_14004F791
0x1400b2958  lea     rax, [rsp+140h+var_F8]
0x1400b295d  mov     dword ptr [rsp+140h+var_F0], 1099h
0x1400b2965  mov     [rbp+40h+var_90], rax
0x1400b2969  lea     rcx, dword_140064110
0x1400b2970  mov     al, [r15+48h]
0x1400b2974  xor     r9d, r9d
0x1400b2977  mov     [rsp+140h+var_100], al
0x1400b297b  xor     r8d, r8d
0x1400b297e  lea     rax, [rsp+140h+var_100]
0x1400b2983  mov     [rbp+40h+var_98], 4
0x1400b298b  mov     [rbp+40h+var_80], rax
0x1400b298f  lea     rax, [rsp+140h+var_E0]
0x1400b2994  mov     [rsp+140h+HandleInformation], rax
0x1400b2999  mov     dword ptr [rsp+140h+Object], 7
0x1400b29a1  mov     [rbp+40h+var_88], 4
0x1400b29a9  mov     [rbp+40h+var_78], 1
0x1400b29b1  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b29b6  jmp     loc_1400B2A8D
0x1400b29bb  mov     r8, cs:__imp_IoFileObjectType
0x1400b29c2  lea     rax, [rsp+140h+var_F8]
0x1400b29c7  mov     rcx, [rcx]; Handle
0x1400b29ca  xor     r9d, r9d; AccessMode
0x1400b29cd  mov     [rsp+140h+HandleInformation], 0; HandleInformation
0x1400b29d6  xor     edx, edx; DesiredAccess
0x1400b29d8  mov     [rsp+140h+var_F8], 0
0x1400b29e1  mov     r8, [r8]; ObjectType
0x1400b29e4  mov     [rsp+140h+Object], rax; Object
0x1400b29e9  call    cs:__imp_ObReferenceObjectByHandle
0x1400b29f0  nop     dword ptr [rax+rax+00h]
0x1400b29f5  mov     r15, [rsp+140h+var_F8]
0x1400b29fa  mov     ebx, eax
0x1400b29fc  test    eax, eax
0x1400b29fe  jns     short loc_1400B2A1E
0x1400b2a00  mov     r9d, eax
0x1400b2a03  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b2a0a  mov     r8d, 10AFh
0x1400b2a10  lea     rcx, aVsmmphustoreme_0; "VsmmPhuStoreMemoryBlockOpenFile"
0x1400b2a17  call    VidTraceErrorStatusInternal0
0x1400b2a1c  jmp     short loc_1400B2A79
0x1400b2a1e  mov     rax, [rsp+140h+var_F0]
0x1400b2a23  mov     r9d, r12d; DesiredAccess
0x1400b2a26  mov     [rsp+140h+Handle], rax; Handle
0x1400b2a2b  xor     r8d, r8d; PassedAccessState
0x1400b2a2e  mov     rax, cs:__imp_IoFileObjectType
0x1400b2a35  xor     edx, edx; HandleAttributes
0x1400b2a37  mov     byte ptr [rsp+140h+HandleInformation], 1; AccessMode
0x1400b2a3c  mov     rcx, [rax]
0x1400b2a3f  mov     [rsp+140h+Object], rcx; ObjectType
0x1400b2a44  mov     rcx, r15; Object
0x1400b2a47  call    cs:__imp_ObOpenObjectByPointer
0x1400b2a4e  nop     dword ptr [rax+rax+00h]
0x1400b2a53  mov     ebx, eax
0x1400b2a55  test    eax, eax
0x1400b2a57  jns     short loc_1400B2A77
0x1400b2a59  mov     r9d, eax
0x1400b2a5c  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b2a63  mov     r8d, 10BDh
0x1400b2a69  lea     rcx, aVsmmphustoreme_0; "VsmmPhuStoreMemoryBlockOpenFile"
0x1400b2a70  call    VidTraceErrorStatusInternal0
0x1400b2a75  jmp     short loc_1400B2A79
0x1400b2a77  xor     ebx, ebx
0x1400b2a79  test    r15, r15
0x1400b2a7c  jz      short loc_1400B2A8D
0x1400b2a7e  mov     rcx, r15; Object
0x1400b2a81  call    cs:__imp_ObfDereferenceObject
0x1400b2a88  nop     dword ptr [rax+rax+00h]
0x1400b2a8d  test    r14, r14
0x1400b2a90  jz      short loc_1400B2A9E
0x1400b2a92  lea     rcx, [r14+80h]
0x1400b2a99  call    VidOpCtrlFinish
0x1400b2a9e  test    ebx, ebx
0x1400b2aa0  jns     loc_1400B2BA1
0x1400b2aa6  mov     eax, cs:dword_140064110
0x1400b2aac  cmp     eax, 2
0x1400b2aaf  jbe     loc_1400B2BA1
0x1400b2ab5  mov     edx, 100h
0x1400b2aba  lea     rcx, dword_140064110
0x1400b2ac1  call    _tlgKeywordOn
0x1400b2ac6  test    al, al
0x1400b2ac8  jz      loc_1400B2BA1
0x1400b2ace  lea     rdx, aVsmmphustoreme_0; "VsmmPhuStoreMemoryBlockOpenFile"
0x1400b2ad5  lea     rcx, [rbp+40h+var_C0]
0x1400b2ad9  call    _tlgCreate1Sz_char
0x1400b2ade  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b2ae5  lea     rcx, [rbp+40h+var_B0]
0x1400b2ae9  call    _tlgCreate1Sz_char
0x1400b2aee  lea     rax, [rsp+140h+var_F8]
0x1400b2af3  mov     dword ptr [rsp+140h+var_F8], 10CEh
0x1400b2afb  mov     [rbp+40h+var_A0], rax
0x1400b2aff  lea     rdx, byte_14004F7EB
0x1400b2b06  lea     rax, [rsp+140h+var_F0]
0x1400b2b0b  mov     [rbp+40h+var_98], 4
0x1400b2b13  mov     [rbp+40h+var_90], rax
0x1400b2b17  lea     rcx, dword_140064110
0x1400b2b1e  lea     rax, [r13+290h]
0x1400b2b25  mov     dword ptr [rsp+140h+var_F0], ebx
0x1400b2b29  mov     [rbp+40h+var_80], rax
0x1400b2b2d  xor     r9d, r9d
0x1400b2b30  lea     rax, [rbp+40h+var_58]
0x1400b2b34  mov     [rbp+40h+var_88], 4
0x1400b2b3c  mov     [rbp+40h+var_70], rax
0x1400b2b40  xor     r8d, r8d
0x1400b2b43  mov     rax, [r13+80h]
0x1400b2b4a  mov     [rbp+40h+var_60], rax
0x1400b2b4e  movzx   eax, word ptr [r13+78h]
0x1400b2b53  mov     [rbp+40h+var_58], eax
0x1400b2b56  mov     rax, [r13+288h]
0x1400b2b5d  mov     [rsp+140h+var_E8], rax
0x1400b2b62  lea     rax, [rsp+140h+var_E8]
0x1400b2b67  mov     [rbp+40h+var_50], rax
0x1400b2b6b  lea     rax, [rsp+140h+var_E0]
0x1400b2b70  mov     [rsp+140h+HandleInformation], rax
0x1400b2b75  mov     dword ptr [rsp+140h+Object], 0Ah
0x1400b2b7d  mov     [rbp+40h+var_78], 10h
0x1400b2b85  mov     [rbp+40h+var_68], 2
0x1400b2b8d  mov     [rbp+40h+var_54], 0
0x1400b2b94  mov     [rbp+40h+var_48], 8
0x1400b2b9c  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b2ba1  mov     eax, ebx
0x1400b2ba3  mov     rcx, [rbp+40h+var_40]
0x1400b2ba7  xor     rcx, rsp; StackCookie
0x1400b2baa  call    __security_check_cookie
0x1400b2baf  add     rsp, 118h
0x1400b2bb6  pop     r15
0x1400b2bb8  pop     r14
0x1400b2bba  pop     r13
0x1400b2bbc  pop     r12
0x1400b2bbe  pop     rbx
0x1400b2bbf  pop     rbp
0x1400b2bc0  retn
```
