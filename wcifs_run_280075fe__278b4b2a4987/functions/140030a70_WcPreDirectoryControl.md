# WcPreDirectoryControl

- ea: `0x140030a70`
- end: `0x140030d4d`
- name: `WcPreDirectoryControl`
- size: `733`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x140001500`
- `0x1400016f0`
- `0x140001bc8`
- `0x140001fd0`
- `0x1400032b8`
- `0x140014c90`
- `0x1400154ac`
- `0x14002ee54`
- `0x140030a70`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140030bc7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140030bc7`
- `FLTMGR!FltLockUserBuffer` at `0x140030b84`
- `FLTMGR!FltLockUserBuffer` at `0x140030b84`
- `FLTMGR!FltReleaseContext` at `0x140030d05`
- `FLTMGR!FltReleaseContext` at `0x140030d1e`
- `FLTMGR!FltReleaseContext` at `0x140030d05`
- `FLTMGR!FltReleaseContext` at `0x140030d1e`

## pseudocode

```c
__int64 __fastcall WcPreDirectoryControl(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  unsigned int v2; // r14d
  __int64 v5; // rbp
  signed int LowPart; // edi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  int Length; // r13d
  int v9; // ecx
  LARGE_INTEGER AllocationSize; // rcx
  PVOID EaBuffer; // rbp
  KPROCESSOR_MODE RequestorMode; // r14
  int v13; // eax
  __int64 v15; // [rsp+48h] [rbp-60h]
  __int64 UnionContext; // [rsp+78h] [rbp-30h]
  char ContextFileObject; // [rsp+B0h] [rbp+8h]
  __int64 v18; // [rsp+C8h] [rbp+20h] BYREF

  LODWORD(v18) = 0;
  v2 = 1;
  if ( CallbackData->Iopb->MinorFunction == 1 )
  {
    UnionContext = WcGetUnionContext(CallbackData, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32));
    v5 = UnionContext;
    if ( UnionContext )
    {
      LowPart = CallbackData->Iopb->Parameters.Read.ByteOffset.LowPart;
      ContextFileObject = WcGetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
      if ( !ContextFileObject )
      {
        if ( LowPart == 33 )
          goto LABEL_20;
        if ( !(unsigned __int8)WcIsInstanceUnionRootDirectory(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32)) )
        {
LABEL_41:
          WcReleaseUnionContext(v5);
          return v2;
        }
      }
      if ( LowPart > 38 )
      {
        if ( LowPart != 60 && LowPart != 63 && LowPart != 78 && LowPart != 79 && (unsigned int)(LowPart - 80) > 1 )
          goto LABEL_41;
      }
      else if ( LowPart != 38
             && LowPart != 1
             && LowPart != 2
             && LowPart != 3
             && LowPart != 12
             && LowPart != 33
             && LowPart != 37 )
      {
        goto LABEL_41;
      }
LABEL_20:
      Iopb = CallbackData->Iopb;
      v2 = 4;
      Length = Iopb->Parameters.Read.Length;
      if ( Iopb->Parameters.Create.AllocationSize.QuadPart )
      {
        v9 = FltLockUserBuffer(CallbackData);
        if ( v9 < 0 )
        {
LABEL_40:
          CallbackData->IoStatus.Status = v9;
          goto LABEL_41;
        }
        AllocationSize = CallbackData->Iopb->Parameters.Create.AllocationSize;
        if ( (*(_BYTE *)(AllocationSize.QuadPart + 10) & 5) != 0 )
          EaBuffer = *(PVOID *)(AllocationSize.QuadPart + 24);
        else
          EaBuffer = MmMapLockedPagesSpecifyCache((PMDL)AllocationSize.QuadPart, 0, MmCached, 0, 0, 0x40000010u);
        if ( !EaBuffer )
        {
          v5 = UnionContext;
          v9 = -1073741801;
          goto LABEL_40;
        }
      }
      else
      {
        EaBuffer = Iopb->Parameters.Create.EaBuffer;
        if ( (CallbackData->Flags & 8) == 0 )
        {
          RequestorMode = CallbackData->RequestorMode;
LABEL_30:
          if ( ContextFileObject
            && (unsigned __int8)WcIsPlaceHolderDirectory(0, 0)
            && (unsigned __int8)WcIsSourcedStream(0)
            && LowPart != 33 )
          {
            v13 = WcEnumerateDirectoryWithMerge(
                    *(PFLT_INSTANCE *)(a2 + 24),
                    *(PFILE_OBJECT *)(a2 + 32),
                    CallbackData->Iopb->Parameters.Create.EaLength,
                    CallbackData->Iopb->OperationFlags,
                    Length,
                    (__int64)EaBuffer,
                    RequestorMode,
                    (__int64)&v18);
            v5 = UnionContext;
          }
          else
          {
            v15 = (__int64)EaBuffer;
            v5 = UnionContext;
            v13 = WcEnumerateDirectoryWithMunge(
                    *(_QWORD *)(a2 + 24),
                    *(_QWORD *)(a2 + 32),
                    LowPart,
                    CallbackData->Iopb->Parameters.QueryEa.EaList,
                    CallbackData->Iopb->Parameters.Create.EaLength,
                    CallbackData->Iopb->OperationFlags,
                    *(_DWORD *)(UnionContext + 36),
                    *(_DWORD *)(UnionContext + 40),
                    Length,
                    v15,
                    RequestorMode,
                    (__int64)&v18);
          }
          v9 = v13;
          if ( (int)(v13 + 0x80000000) < 0 || v13 == -2147483643 )
            CallbackData->IoStatus.Information = (unsigned int)v18;
          v2 = 4;
          goto LABEL_40;
        }
      }
      RequestorMode = 0;
      goto LABEL_30;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140030a70  mov     rax, rsp
0x140030a73  mov     [rax+10h], rbx
0x140030a77  push    rbp
0x140030a78  push    rsi
0x140030a79  push    rdi
0x140030a7a  push    r13
0x140030a7c  push    r14
0x140030a7e  sub     rsp, 80h
0x140030a85  mov     dword ptr [rax+20h], 0
0x140030a8c  mov     r14d, 1
0x140030a92  mov     qword ptr [rax-38h], 0
0x140030a9a  mov     rsi, rdx
0x140030a9d  mov     qword ptr [rax-40h], 0
0x140030aa5  mov     rbx, rcx
0x140030aa8  mov     rax, [rcx+10h]
0x140030aac  cmp     [rax+5], r14b
0x140030ab0  jnz     loc_140030D32
0x140030ab6  mov     r8, [rdx+20h]
0x140030aba  mov     rdx, [rdx+18h]
0x140030abe  call    WcGetUnionContext
0x140030ac3  mov     [rsp+0A8h+var_30], rax
0x140030ac8  mov     rbp, rax
0x140030acb  test    rax, rax
0x140030ace  jz      loc_140030D32
0x140030ad4  mov     rax, [rbx+10h]
0x140030ad8  lea     r9, [rsp+0A8h+Context]
0x140030add  mov     rdx, [rsi+20h]; FileObject
0x140030ae1  lea     r8, [rsp+0A8h+var_38]
0x140030ae6  mov     rcx, [rsi+18h]; Instance
0x140030aea  mov     edi, [rax+28h]
0x140030aed  call    WcGetContextFileObject
0x140030af2  mov     [rsp+0A8h+arg_0], al
0x140030af9  test    al, al
0x140030afb  jnz     short loc_140030B17
0x140030afd  cmp     edi, 21h ; '!'
0x140030b00  jz      short loc_140030B67
0x140030b02  mov     rdx, [rsi+20h]; FileObject
0x140030b06  mov     rcx, [rsi+18h]; Instance
0x140030b0a  call    WcIsInstanceUnionRootDirectory
0x140030b0f  test    al, al
0x140030b11  jz      loc_140030CF8
0x140030b17  cmp     edi, 26h ; '&'
0x140030b1a  jg      short loc_140030B43
0x140030b1c  jz      short loc_140030B67
0x140030b1e  mov     ecx, edi
0x140030b20  sub     ecx, r14d
0x140030b23  jz      short loc_140030B67
0x140030b25  sub     ecx, r14d
0x140030b28  jz      short loc_140030B67
0x140030b2a  sub     ecx, r14d
0x140030b2d  jz      short loc_140030B67
0x140030b2f  sub     ecx, 9
0x140030b32  jz      short loc_140030B67
0x140030b34  sub     ecx, 15h
0x140030b37  jz      short loc_140030B67
0x140030b39  cmp     ecx, 4
0x140030b3c  jz      short loc_140030B67
0x140030b3e  jmp     loc_140030CF8
0x140030b43  mov     ecx, edi
0x140030b45  sub     ecx, 3Ch ; '<'
0x140030b48  jz      short loc_140030B67
0x140030b4a  sub     ecx, 3
0x140030b4d  jz      short loc_140030B67
0x140030b4f  sub     ecx, 0Fh
0x140030b52  jz      short loc_140030B67
0x140030b54  sub     ecx, r14d
0x140030b57  jz      short loc_140030B67
0x140030b59  sub     ecx, r14d
0x140030b5c  jz      short loc_140030B67
0x140030b5e  cmp     ecx, r14d
0x140030b61  jnz     loc_140030CF8
0x140030b67  mov     rax, [rbx+10h]
0x140030b6b  mov     r14d, 4
0x140030b71  mov     [rsp+0A8h+var_48], r14d
0x140030b76  cmp     qword ptr [rax+40h], 0
0x140030b7b  mov     r13d, [rax+18h]
0x140030b7f  jz      short loc_140030BEA
0x140030b81  mov     rcx, rbx; CallbackData
0x140030b84  call    cs:__imp_FltLockUserBuffer
0x140030b8b  nop     dword ptr [rax+rax+00h]
0x140030b90  mov     ecx, eax
0x140030b92  test    eax, eax
0x140030b94  js      loc_140030CF5
0x140030b9a  mov     rax, [rbx+10h]
0x140030b9e  mov     rcx, [rax+40h]; MemoryDescriptorList
0x140030ba2  test    byte ptr [rcx+0Ah], 5
0x140030ba6  jz      short loc_140030BAE
0x140030ba8  mov     rbp, [rcx+18h]
0x140030bac  jmp     short loc_140030BD6
0x140030bae  xor     r9d, r9d; RequestedAddress
0x140030bb1  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x140030bb9  xor     edx, edx; AccessMode
0x140030bbb  mov     [rsp+0A8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140030bc3  lea     r8d, [r9+1]; CacheType
0x140030bc7  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140030bce  nop     dword ptr [rax+rax+00h]
0x140030bd3  mov     rbp, rax
0x140030bd6  test    rbp, rbp
0x140030bd9  jnz     short loc_140030BF4
0x140030bdb  mov     rbp, [rsp+0A8h+var_30]
0x140030be0  mov     ecx, 0C0000017h
0x140030be5  jmp     loc_140030CF5
0x140030bea  mov     rbp, [rax+38h]
0x140030bee  mov     eax, [rbx]
0x140030bf0  test    al, 8
0x140030bf2  jz      short loc_140030BF9
0x140030bf4  xor     r14b, r14b
0x140030bf7  jmp     short loc_140030BFD
0x140030bf9  mov     r14b, [rbx+50h]
0x140030bfd  cmp     [rsp+0A8h+arg_0], 0
0x140030c05  jz      short loc_140030C78
0x140030c07  mov     rdx, [rsp+0A8h+Context]
0x140030c0c  mov     rcx, [rsp+0A8h+var_38]
0x140030c11  call    WcIsPlaceHolderDirectory
0x140030c16  test    al, al
0x140030c18  jz      short loc_140030C78
0x140030c1a  mov     rcx, [rsp+0A8h+Context]
0x140030c1f  call    WcIsSourcedStream
0x140030c24  test    al, al
0x140030c26  jz      short loc_140030C78
0x140030c28  cmp     edi, 21h ; '!'
0x140030c2b  jz      short loc_140030C78
0x140030c2d  mov     r9, [rbx+10h]
0x140030c31  lea     rax, [rsp+0A8h+arg_18]
0x140030c39  mov     rdx, [rsi+20h]; FileObject
0x140030c3d  mov     r8d, edi
0x140030c40  mov     rcx, [rsi+18h]; Instance
0x140030c44  mov     [rsp+0A8h+var_60], rax; __int64
0x140030c49  mov     al, [r9+6]
0x140030c4d  mov     [rsp+0A8h+var_68], r14b; char
0x140030c52  mov     [rsp+0A8h+var_70], rbp; __int64
0x140030c57  mov     [rsp+0A8h+var_78], r13d; int
0x140030c5c  mov     byte ptr [rsp+0A8h+Priority], al; char
0x140030c60  mov     eax, [r9+30h]
0x140030c64  mov     r9, [r9+20h]
0x140030c68  mov     [rsp+0A8h+BugCheckOnFailure], eax; int
0x140030c6c  call    WcEnumerateDirectoryWithMerge
0x140030c71  mov     rbp, [rsp+0A8h+var_30]
0x140030c76  jmp     short loc_140030CCF
0x140030c78  mov     r9, [rbx+10h]
0x140030c7c  lea     rax, [rsp+0A8h+arg_18]
0x140030c84  mov     rdx, [rsi+20h]
0x140030c88  mov     r8d, edi
0x140030c8b  mov     rcx, [rsi+18h]
0x140030c8f  mov     [rsp+0A8h+var_50], rax
0x140030c94  mov     [rsp+0A8h+var_58], r14b
0x140030c99  mov     [rsp+0A8h+var_60], rbp
0x140030c9e  mov     rbp, [rsp+0A8h+var_30]
0x140030ca3  mov     dword ptr [rsp+0A8h+var_68], r13d
0x140030ca8  mov     eax, [rbp+28h]
0x140030cab  mov     dword ptr [rsp+0A8h+var_70], eax
0x140030caf  mov     eax, [rbp+24h]
0x140030cb2  mov     [rsp+0A8h+var_78], eax
0x140030cb6  mov     al, [r9+6]
0x140030cba  mov     byte ptr [rsp+0A8h+Priority], al
0x140030cbe  mov     eax, [r9+30h]
0x140030cc2  mov     r9, [r9+20h]
0x140030cc6  mov     [rsp+0A8h+BugCheckOnFailure], eax
0x140030cca  call    WcEnumerateDirectoryWithMunge
0x140030ccf  mov     edx, 80000000h
0x140030cd4  mov     ecx, eax
0x140030cd6  lea     eax, [rax+rdx]
0x140030cd9  test    edx, eax
0x140030cdb  jnz     short loc_140030CE5
0x140030cdd  cmp     ecx, 80000005h
0x140030ce3  jnz     short loc_140030CF0
0x140030ce5  mov     eax, dword ptr [rsp+0A8h+arg_18]
0x140030cec  mov     [rbx+20h], rax
0x140030cf0  mov     r14d, [rsp+0A8h+var_48]
0x140030cf5  mov     [rbx+18h], ecx
0x140030cf8  cmp     [rsp+0A8h+Context], 0
0x140030cfe  jz      short loc_140030D11
0x140030d00  mov     rcx, [rsp+0A8h+Context]; Context
0x140030d05  call    cs:__imp_FltReleaseContext
0x140030d0c  nop     dword ptr [rax+rax+00h]
0x140030d11  cmp     [rsp+0A8h+var_38], 0
0x140030d17  jz      short loc_140030D2A
0x140030d19  mov     rcx, [rsp+0A8h+var_38]; Context
0x140030d1e  call    cs:__imp_FltReleaseContext
0x140030d25  nop     dword ptr [rax+rax+00h]
0x140030d2a  mov     rcx, rbp
0x140030d2d  call    WcReleaseUnionContext
0x140030d32  mov     rbx, [rsp+0A8h+arg_8]
0x140030d3a  mov     eax, r14d
0x140030d3d  add     rsp, 80h
0x140030d44  pop     r14
0x140030d46  pop     r13
0x140030d48  pop     rdi
0x140030d49  pop     rsi
0x140030d4a  pop     rbp
0x140030d4b  retn
```
