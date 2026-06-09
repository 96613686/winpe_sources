# WcPreDirectoryControl

- ea: `0x140030ac0`
- end: `0x140030d9d`
- name: `WcPreDirectoryControl`
- size: `733`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64)`
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
- `0x14002eea4`
- `0x140030ac0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140030c17`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140030c17`
- `FLTMGR!FltLockUserBuffer` at `0x140030bd4`
- `FLTMGR!FltLockUserBuffer` at `0x140030bd4`
- `FLTMGR!FltReleaseContext` at `0x140030d55`
- `FLTMGR!FltReleaseContext` at `0x140030d6e`
- `FLTMGR!FltReleaseContext` at `0x140030d55`
- `FLTMGR!FltReleaseContext` at `0x140030d6e`

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
0x140030ac0  mov     rax, rsp
0x140030ac3  mov     [rax+10h], rbx
0x140030ac7  push    rbp
0x140030ac8  push    rsi
0x140030ac9  push    rdi
0x140030aca  push    r13
0x140030acc  push    r14
0x140030ace  sub     rsp, 80h
0x140030ad5  mov     dword ptr [rax+20h], 0
0x140030adc  mov     r14d, 1
0x140030ae2  mov     qword ptr [rax-38h], 0
0x140030aea  mov     rsi, rdx
0x140030aed  mov     qword ptr [rax-40h], 0
0x140030af5  mov     rbx, rcx
0x140030af8  mov     rax, [rcx+10h]
0x140030afc  cmp     [rax+5], r14b
0x140030b00  jnz     loc_140030D82
0x140030b06  mov     r8, [rdx+20h]
0x140030b0a  mov     rdx, [rdx+18h]
0x140030b0e  call    WcGetUnionContext
0x140030b13  mov     [rsp+0A8h+var_30], rax
0x140030b18  mov     rbp, rax
0x140030b1b  test    rax, rax
0x140030b1e  jz      loc_140030D82
0x140030b24  mov     rax, [rbx+10h]
0x140030b28  lea     r9, [rsp+0A8h+Context]
0x140030b2d  mov     rdx, [rsi+20h]; FileObject
0x140030b31  lea     r8, [rsp+0A8h+var_38]
0x140030b36  mov     rcx, [rsi+18h]; Instance
0x140030b3a  mov     edi, [rax+28h]
0x140030b3d  call    WcGetContextFileObject
0x140030b42  mov     [rsp+0A8h+arg_0], al
0x140030b49  test    al, al
0x140030b4b  jnz     short loc_140030B67
0x140030b4d  cmp     edi, 21h ; '!'
0x140030b50  jz      short loc_140030BB7
0x140030b52  mov     rdx, [rsi+20h]; FileObject
0x140030b56  mov     rcx, [rsi+18h]; Instance
0x140030b5a  call    WcIsInstanceUnionRootDirectory
0x140030b5f  test    al, al
0x140030b61  jz      loc_140030D48
0x140030b67  cmp     edi, 26h ; '&'
0x140030b6a  jg      short loc_140030B93
0x140030b6c  jz      short loc_140030BB7
0x140030b6e  mov     ecx, edi
0x140030b70  sub     ecx, r14d
0x140030b73  jz      short loc_140030BB7
0x140030b75  sub     ecx, r14d
0x140030b78  jz      short loc_140030BB7
0x140030b7a  sub     ecx, r14d
0x140030b7d  jz      short loc_140030BB7
0x140030b7f  sub     ecx, 9
0x140030b82  jz      short loc_140030BB7
0x140030b84  sub     ecx, 15h
0x140030b87  jz      short loc_140030BB7
0x140030b89  cmp     ecx, 4
0x140030b8c  jz      short loc_140030BB7
0x140030b8e  jmp     loc_140030D48
0x140030b93  mov     ecx, edi
0x140030b95  sub     ecx, 3Ch ; '<'
0x140030b98  jz      short loc_140030BB7
0x140030b9a  sub     ecx, 3
0x140030b9d  jz      short loc_140030BB7
0x140030b9f  sub     ecx, 0Fh
0x140030ba2  jz      short loc_140030BB7
0x140030ba4  sub     ecx, r14d
0x140030ba7  jz      short loc_140030BB7
0x140030ba9  sub     ecx, r14d
0x140030bac  jz      short loc_140030BB7
0x140030bae  cmp     ecx, r14d
0x140030bb1  jnz     loc_140030D48
0x140030bb7  mov     rax, [rbx+10h]
0x140030bbb  mov     r14d, 4
0x140030bc1  mov     [rsp+0A8h+var_48], r14d
0x140030bc6  cmp     qword ptr [rax+40h], 0
0x140030bcb  mov     r13d, [rax+18h]
0x140030bcf  jz      short loc_140030C3A
0x140030bd1  mov     rcx, rbx; CallbackData
0x140030bd4  call    cs:__imp_FltLockUserBuffer
0x140030bdb  nop     dword ptr [rax+rax+00h]
0x140030be0  mov     ecx, eax
0x140030be2  test    eax, eax
0x140030be4  js      loc_140030D45
0x140030bea  mov     rax, [rbx+10h]
0x140030bee  mov     rcx, [rax+40h]; MemoryDescriptorList
0x140030bf2  test    byte ptr [rcx+0Ah], 5
0x140030bf6  jz      short loc_140030BFE
0x140030bf8  mov     rbp, [rcx+18h]
0x140030bfc  jmp     short loc_140030C26
0x140030bfe  xor     r9d, r9d; RequestedAddress
0x140030c01  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x140030c09  xor     edx, edx; AccessMode
0x140030c0b  mov     [rsp+0A8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140030c13  lea     r8d, [r9+1]; CacheType
0x140030c17  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140030c1e  nop     dword ptr [rax+rax+00h]
0x140030c23  mov     rbp, rax
0x140030c26  test    rbp, rbp
0x140030c29  jnz     short loc_140030C44
0x140030c2b  mov     rbp, [rsp+0A8h+var_30]
0x140030c30  mov     ecx, 0C0000017h
0x140030c35  jmp     loc_140030D45
0x140030c3a  mov     rbp, [rax+38h]
0x140030c3e  mov     eax, [rbx]
0x140030c40  test    al, 8
0x140030c42  jz      short loc_140030C49
0x140030c44  xor     r14b, r14b
0x140030c47  jmp     short loc_140030C4D
0x140030c49  mov     r14b, [rbx+50h]
0x140030c4d  cmp     [rsp+0A8h+arg_0], 0
0x140030c55  jz      short loc_140030CC8
0x140030c57  mov     rdx, [rsp+0A8h+Context]
0x140030c5c  mov     rcx, [rsp+0A8h+var_38]
0x140030c61  call    WcIsPlaceHolderDirectory
0x140030c66  test    al, al
0x140030c68  jz      short loc_140030CC8
0x140030c6a  mov     rcx, [rsp+0A8h+Context]
0x140030c6f  call    WcIsSourcedStream
0x140030c74  test    al, al
0x140030c76  jz      short loc_140030CC8
0x140030c78  cmp     edi, 21h ; '!'
0x140030c7b  jz      short loc_140030CC8
0x140030c7d  mov     r9, [rbx+10h]
0x140030c81  lea     rax, [rsp+0A8h+arg_18]
0x140030c89  mov     rdx, [rsi+20h]; FileObject
0x140030c8d  mov     r8d, edi
0x140030c90  mov     rcx, [rsi+18h]; Instance
0x140030c94  mov     [rsp+0A8h+var_60], rax; __int64
0x140030c99  mov     al, [r9+6]
0x140030c9d  mov     [rsp+0A8h+var_68], r14b; char
0x140030ca2  mov     [rsp+0A8h+var_70], rbp; __int64
0x140030ca7  mov     [rsp+0A8h+var_78], r13d; int
0x140030cac  mov     byte ptr [rsp+0A8h+Priority], al; char
0x140030cb0  mov     eax, [r9+30h]
0x140030cb4  mov     r9, [r9+20h]
0x140030cb8  mov     [rsp+0A8h+BugCheckOnFailure], eax; int
0x140030cbc  call    WcEnumerateDirectoryWithMerge
0x140030cc1  mov     rbp, [rsp+0A8h+var_30]
0x140030cc6  jmp     short loc_140030D1F
0x140030cc8  mov     r9, [rbx+10h]
0x140030ccc  lea     rax, [rsp+0A8h+arg_18]
0x140030cd4  mov     rdx, [rsi+20h]
0x140030cd8  mov     r8d, edi
0x140030cdb  mov     rcx, [rsi+18h]
0x140030cdf  mov     [rsp+0A8h+var_50], rax
0x140030ce4  mov     [rsp+0A8h+var_58], r14b
0x140030ce9  mov     [rsp+0A8h+var_60], rbp
0x140030cee  mov     rbp, [rsp+0A8h+var_30]
0x140030cf3  mov     dword ptr [rsp+0A8h+var_68], r13d
0x140030cf8  mov     eax, [rbp+28h]
0x140030cfb  mov     dword ptr [rsp+0A8h+var_70], eax
0x140030cff  mov     eax, [rbp+24h]
0x140030d02  mov     [rsp+0A8h+var_78], eax
0x140030d06  mov     al, [r9+6]
0x140030d0a  mov     byte ptr [rsp+0A8h+Priority], al
0x140030d0e  mov     eax, [r9+30h]
0x140030d12  mov     r9, [r9+20h]
0x140030d16  mov     [rsp+0A8h+BugCheckOnFailure], eax
0x140030d1a  call    WcEnumerateDirectoryWithMunge
0x140030d1f  mov     edx, 80000000h
0x140030d24  mov     ecx, eax
0x140030d26  lea     eax, [rax+rdx]
0x140030d29  test    edx, eax
0x140030d2b  jnz     short loc_140030D35
0x140030d2d  cmp     ecx, 80000005h
0x140030d33  jnz     short loc_140030D40
0x140030d35  mov     eax, dword ptr [rsp+0A8h+arg_18]
0x140030d3c  mov     [rbx+20h], rax
0x140030d40  mov     r14d, [rsp+0A8h+var_48]
0x140030d45  mov     [rbx+18h], ecx
0x140030d48  cmp     [rsp+0A8h+Context], 0
0x140030d4e  jz      short loc_140030D61
0x140030d50  mov     rcx, [rsp+0A8h+Context]; Context
0x140030d55  call    cs:__imp_FltReleaseContext
0x140030d5c  nop     dword ptr [rax+rax+00h]
0x140030d61  cmp     [rsp+0A8h+var_38], 0
0x140030d67  jz      short loc_140030D7A
0x140030d69  mov     rcx, [rsp+0A8h+var_38]; Context
0x140030d6e  call    cs:__imp_FltReleaseContext
0x140030d75  nop     dword ptr [rax+rax+00h]
0x140030d7a  mov     rcx, rbp
0x140030d7d  call    WcReleaseUnionContext
0x140030d82  mov     rbx, [rsp+0A8h+arg_8]
0x140030d8a  mov     eax, r14d
0x140030d8d  add     rsp, 80h
0x140030d94  pop     r14
0x140030d96  pop     r13
0x140030d98  pop     rdi
0x140030d99  pop     rsi
0x140030d9a  pop     rbp
0x140030d9b  retn
```
