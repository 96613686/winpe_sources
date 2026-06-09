# WofPreDirectoryControlCallback

- ea: `0x140036e20`
- end: `0x14003768e`
- name: `WofPreDirectoryControlCallback`
- size: `2158`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, loader_planting`

## callees

- `0x1400014d0`
- `0x14002378c`
- `0x14002382c`
- `0x140036e20`
- `0x1400376a0`
- `0x140037cd0`
- `0x14003ba0c`
- `0x14003befc`
- `0x14003e068`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140037270`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400372c3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140037270`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400372c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400370c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400370c6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036f0a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003730c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036f0a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003730c`
- `FLTMGR!FltPerformSynchronousIo` at `0x140036ff0`
- `FLTMGR!FltPerformSynchronousIo` at `0x14003744b`
- `FLTMGR!FltPerformSynchronousIo` at `0x140036ff0`
- `FLTMGR!FltPerformSynchronousIo` at `0x14003744b`
- `FLTMGR!FltLockUserBuffer` at `0x140037212`
- `FLTMGR!FltLockUserBuffer` at `0x1400375b9`
- `FLTMGR!FltLockUserBuffer` at `0x140037212`
- `FLTMGR!FltLockUserBuffer` at `0x1400375b9`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x140036f36`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x14003736b`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x140036f36`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x14003736b`
- `FLTMGR!FltPropagateIrpExtension` at `0x140036f54`
- `FLTMGR!FltPropagateIrpExtension` at `0x140037389`
- `FLTMGR!FltPropagateIrpExtension` at `0x140036f54`
- `FLTMGR!FltPropagateIrpExtension` at `0x140037389`
- `FLTMGR!FltFreeCallbackData` at `0x140037009`
- `FLTMGR!FltFreeCallbackData` at `0x140037465`
- `FLTMGR!FltFreeCallbackData` at `0x140037675`
- `FLTMGR!FltFreeCallbackData` at `0x140037009`
- `FLTMGR!FltFreeCallbackData` at `0x140037465`
- `FLTMGR!FltFreeCallbackData` at `0x140037675`
- `FLTMGR!FltReleaseContext` at `0x140036e8e`
- `FLTMGR!FltReleaseContext` at `0x140037125`
- `FLTMGR!FltReleaseContext` at `0x140036e8e`
- `FLTMGR!FltReleaseContext` at `0x140037125`

## pseudocode

```c
__int64 __fastcall WofPreDirectoryControlCallback(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  unsigned int v3; // ebx
  int VolumeContext; // r14d
  PVOID PoolWithTag; // r15
  PFLT_IO_PARAMETER_BLOCK v8; // rdi
  unsigned __int64 LowPart; // r13
  unsigned __int64 v10; // rcx
  unsigned int v11; // r8d
  unsigned int v12; // edx
  DWORD v13; // r14d
  unsigned int v14; // edi
  ULONG v15; // edi
  int v16; // eax
  NTSTATUS v17; // eax
  NTSTATUS Status; // edi
  NTSTATUS v19; // r12d
  PFLT_IO_PARAMETER_BLOCK v20; // rax
  ULONG v21; // edi
  PVOID v22; // r9
  KPROCESSOR_MODE RequestorMode; // cl
  DWORD v24; // r14d
  DWORD v25; // r14d
  DWORD v26; // r14d
  DWORD v27; // r14d
  NTSTATUS v29; // eax
  int v30; // eax
  LARGE_INTEGER AllocationSize; // rcx
  char *v32; // r13
  LARGE_INTEGER v33; // rcx
  unsigned int v34; // ecx
  ULONG v35; // edi
  bool v36; // r13
  struct _FILE_OBJECT *v37; // rdx
  struct _FLT_INSTANCE *v38; // rcx
  PFLT_IO_PARAMETER_BLOCK v39; // rcx
  int v40; // eax
  ULONG Priority; // [rsp+28h] [rbp-48h]
  char v42; // [rsp+40h] [rbp-30h]
  unsigned int v43; // [rsp+44h] [rbp-2Ch] BYREF
  ULONG Length; // [rsp+48h] [rbp-28h]
  unsigned int Information; // [rsp+4Ch] [rbp-24h]
  ULONG v46; // [rsp+50h] [rbp-20h]
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+58h] [rbp-18h] BYREF
  char *EaBuffer; // [rsp+60h] [rbp-10h]
  unsigned int Context; // [rsp+B0h] [rbp+40h]
  unsigned __int8 Contexta; // [rsp+B0h] [rbp+40h]
  UCHAR OperationFlags; // [rsp+C8h] [rbp+58h]

  Iopb = CallbackData->Iopb;
  RetNewCallbackData = 0;
  v3 = 1;
  v43 = 0;
  if ( Iopb->MinorFunction != 1 )
    return v3;
  VolumeContext = WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24));
  if ( VolumeContext >= 0 )
  {
    if ( (MEMORY[0x38] & 1) == 0 )
    {
      PoolWithTag = 0;
      FltReleaseContext(0);
      v8 = CallbackData->Iopb;
      LowPart = v8->Parameters.Read.ByteOffset.LowPart;
      if ( (unsigned int)LowPart > 0x3F || (v10 = 0x900000600000000EuLL, !_bittest64((const __int64 *)&v10, LowPart)) )
      {
        if ( (unsigned int)(LowPart - 78) > 3 )
        {
          if ( (_DWORD)LowPart != 33 || !byte_140018454 )
            goto LABEL_29;
          v3 = 4;
          OperationFlags = v8->OperationFlags;
          Length = v8->Parameters.Read.Length;
          if ( v8->Parameters.Create.AllocationSize.QuadPart )
          {
            v30 = FltLockUserBuffer(CallbackData);
            VolumeContext = v30;
            if ( v30 < 0 )
            {
              CallbackData->IoStatus.Status = v30;
              goto LABEL_29;
            }
            AllocationSize = CallbackData->Iopb->Parameters.Create.AllocationSize;
            if ( (*(_BYTE *)(AllocationSize.QuadPart + 10) & 5) != 0 )
              v32 = *(char **)(AllocationSize.QuadPart + 24);
            else
              v32 = (char *)MmMapLockedPagesSpecifyCache((PMDL)AllocationSize.QuadPart, 0, MmCached, 0, 0, 0x40000010u);
            EaBuffer = v32;
            if ( !v32 )
            {
              CallbackData->IoStatus.Status = -1073741801;
              goto LABEL_29;
            }
          }
          else
          {
            EaBuffer = (char *)v8->Parameters.Create.EaBuffer;
            if ( (CallbackData->Flags & 8) == 0 )
            {
              Contexta = CallbackData->RequestorMode;
              goto LABEL_64;
            }
          }
          Contexta = 0;
LABEL_64:
          v34 = v8->Parameters.Read.Length;
          if ( v34 > 0x10000 )
            v34 = 0x10000;
          v46 = v34;
          PoolWithTag = ExAllocatePoolWithTag(PagedPool, v34, 0x44666F57u);
          if ( PoolWithTag )
          {
            v35 = 0;
            v42 = 1;
            v36 = 0;
            while ( VolumeContext >= 0 && !v36 && v35 < Length )
            {
              v37 = *(struct _FILE_OBJECT **)(a2 + 32);
              v38 = *(struct _FLT_INSTANCE **)(a2 + 24);
              v43 = 0;
              v16 = FltAllocateCallbackDataEx(v38, v37, 1u, &RetNewCallbackData);
              if ( v16 < 0 )
                goto LABEL_96;
              v16 = FltPropagateIrpExtension(CallbackData, RetNewCallbackData, 0);
              if ( v16 < 0 )
                goto LABEL_96;
              RetNewCallbackData->Iopb->MajorFunction = 12;
              RetNewCallbackData->Iopb->MinorFunction = 1;
              RetNewCallbackData->Iopb->Parameters.Read.Length = v46;
              RetNewCallbackData->Iopb->Parameters.Read.ByteOffset.LowPart = 33;
              v39 = RetNewCallbackData->Iopb;
              if ( v42 )
              {
                v39->Parameters.QueryEa.EaList = CallbackData->Iopb->Parameters.QueryEa.EaList;
                RetNewCallbackData->Iopb->Parameters.Create.EaLength = CallbackData->Iopb->Parameters.Create.EaLength;
              }
              else
              {
                v39->Parameters.QueryEa.EaList = 0;
                RetNewCallbackData->Iopb->Parameters.Create.EaLength = 0;
              }
              RetNewCallbackData->Iopb->Parameters.Create.EaBuffer = PoolWithTag;
              RetNewCallbackData->Iopb->Parameters.Create.AllocationSize.QuadPart = 0;
              RetNewCallbackData->Iopb->OperationFlags = OperationFlags;
              OperationFlags &= 0xFAu;
              FltPerformSynchronousIo(RetNewCallbackData);
              VolumeContext = RetNewCallbackData->IoStatus.Status;
              Information = RetNewCallbackData->IoStatus.Information;
              FltFreeCallbackData(RetNewCallbackData);
              RetNewCallbackData = 0;
              CallbackData->IoStatus.Status = VolumeContext;
              if ( VolumeContext == -2147483642 )
              {
                if ( v35 + Information )
                {
                  CallbackData->IoStatus.Status = 0;
                  v36 = 1;
                }
              }
              else if ( VolumeContext >= 0 )
              {
                LOBYTE(Priority) = Contexta;
                v16 = WofFilterReparseEnumerate(
                        Contexta,
                        PoolWithTag,
                        Information,
                        &EaBuffer[v35],
                        Length - v35,
                        Priority,
                        &v43);
                VolumeContext = v16;
                if ( v16 < 0 )
                  goto LABEL_96;
                v35 += v43;
                v36 = Length - v35 < 0x10;
                if ( (OperationFlags & 2) != 0 && v43 )
                  v36 = 1;
              }
              v42 = 0;
            }
            CallbackData->IoStatus.Information = v35;
          }
          else
          {
            CallbackData->IoStatus.Status = -1073741670;
          }
LABEL_29:
          if ( RetNewCallbackData )
          {
            FltFreeCallbackData(RetNewCallbackData);
            RetNewCallbackData = 0;
          }
          if ( !PoolWithTag )
            return v3;
          goto LABEL_32;
        }
      }
      v11 = 0;
      v12 = 0;
      v13 = 0;
      v3 = 4;
      switch ( (int)LowPart )
      {
        case 1:
          v12 = 80;
          v11 = 64;
          v13 = 78;
          break;
        case 2:
          v12 = 80;
          v11 = 68;
          v13 = 78;
          break;
        case 3:
          v12 = 106;
          v11 = 94;
          v13 = 79;
          break;
        case 37:
          v12 = 106;
          v11 = 104;
          v13 = 79;
          break;
        case 38:
        case 78:
          v11 = 80;
          v12 = 80;
          v13 = 78;
          break;
        case 60:
          v11 = 88;
          v13 = 60;
          goto LABEL_94;
        case 63:
          v11 = 114;
          v13 = 63;
          goto LABEL_94;
        case 79:
          v12 = 106;
          v13 = 79;
          v11 = 106;
          break;
        case 80:
          v11 = 96;
          v13 = 80;
          goto LABEL_94;
        case 81:
          v11 = 122;
          v13 = 81;
LABEL_94:
          v12 = v11;
          break;
        default:
          break;
      }
      v14 = v12 + v8->Parameters.Read.Length;
      if ( v14 < v12 || v14 < v11 )
      {
        CallbackData->IoStatus.Status = -1073741811;
        goto LABEL_29;
      }
      v15 = v14 - v11;
      if ( v15 > 0x10000 )
        v15 = 0x10000;
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, v15, 0x44666F57u);
      if ( !PoolWithTag )
      {
        CallbackData->IoStatus.Status = -1073741670;
        goto LABEL_29;
      }
      v16 = FltAllocateCallbackDataEx(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), 1u, &RetNewCallbackData);
      if ( v16 < 0 )
      {
LABEL_96:
        CallbackData->IoStatus.Status = v16;
        goto LABEL_29;
      }
      v17 = FltPropagateIrpExtension(CallbackData, RetNewCallbackData, 0);
      if ( v17 < 0 )
      {
        CallbackData->IoStatus.Status = v17;
        goto LABEL_29;
      }
      RetNewCallbackData->Iopb->MajorFunction = 12;
      RetNewCallbackData->Iopb->MinorFunction = 1;
      RetNewCallbackData->Iopb->Parameters.Read.Length = v15;
      RetNewCallbackData->Iopb->Parameters.Read.ByteOffset.LowPart = v13;
      RetNewCallbackData->Iopb->Parameters.QueryEa.EaList = CallbackData->Iopb->Parameters.QueryEa.EaList;
      RetNewCallbackData->Iopb->Parameters.Create.EaLength = CallbackData->Iopb->Parameters.Create.EaLength;
      RetNewCallbackData->Iopb->Parameters.Create.EaBuffer = PoolWithTag;
      RetNewCallbackData->Iopb->Parameters.Create.AllocationSize.QuadPart = 0;
      RetNewCallbackData->Iopb->OperationFlags = CallbackData->Iopb->OperationFlags;
      FltPerformSynchronousIo(RetNewCallbackData);
      Status = RetNewCallbackData->IoStatus.Status;
      Context = RetNewCallbackData->IoStatus.Information;
      FltFreeCallbackData(RetNewCallbackData);
      v19 = 0;
      RetNewCallbackData = 0;
      CallbackData->IoStatus.Status = Status;
      if ( Status != -2147483643 )
        v19 = Status;
      if ( v19 < 0 )
      {
LABEL_32:
        ExFreePoolWithTag(PoolWithTag, 0);
        return v3;
      }
      v20 = CallbackData->Iopb;
      v21 = v20->Parameters.Read.Length;
      if ( v20->Parameters.Create.AllocationSize.QuadPart )
      {
        v40 = FltLockUserBuffer(CallbackData);
        v19 = v40;
        if ( v40 < 0 )
        {
          CallbackData->IoStatus.Status = v40;
          goto LABEL_29;
        }
        v33 = CallbackData->Iopb->Parameters.Create.AllocationSize;
        if ( (*(_BYTE *)(v33.QuadPart + 10) & 5) != 0 )
          v22 = *(PVOID *)(v33.QuadPart + 24);
        else
          v22 = MmMapLockedPagesSpecifyCache((PMDL)v33.QuadPart, 0, MmCached, 0, 0, 0x40000010u);
        if ( !v22 )
        {
          CallbackData->IoStatus.Status = -1073741801;
          goto LABEL_29;
        }
      }
      else
      {
        v22 = v20->Parameters.Create.EaBuffer;
        if ( (CallbackData->Flags & 8) == 0 )
        {
          RequestorMode = CallbackData->RequestorMode;
          goto LABEL_20;
        }
      }
      RequestorMode = 0;
LABEL_20:
      if ( v13 == 79 )
      {
        LOBYTE(Priority) = RequestorMode;
        v29 = WofMungeDirectoryEnumerateWithShortnameFileId64(
                (unsigned int)LowPart,
                PoolWithTag,
                Context,
                v22,
                v21,
                Priority,
                &v43);
      }
      else
      {
        v24 = v13 - 60;
        if ( v24 )
        {
          v25 = v24 - 3;
          if ( v25 )
          {
            v26 = v25 - 15;
            if ( !v26 )
            {
              LOBYTE(Priority) = RequestorMode;
              v19 = WofMungeDirectoryEnumerateWithoutShortnameFileId64(
                      (unsigned int)LowPart,
                      PoolWithTag,
                      Context,
                      v22,
                      v21,
                      Priority,
                      &v43);
LABEL_26:
              if ( v19 < 0 )
                CallbackData->IoStatus.Status = v19;
              else
                CallbackData->IoStatus.Information = v43;
              goto LABEL_29;
            }
            v27 = v26 - 2;
            if ( v27 )
            {
              if ( v27 != 1 )
                goto LABEL_26;
              LOBYTE(Priority) = RequestorMode;
              v29 = WofMungeDirectoryEnumerateWithShortnameFileIdAll(
                      (unsigned int)LowPart,
                      PoolWithTag,
                      Context,
                      v22,
                      v21,
                      Priority,
                      &v43);
            }
            else
            {
              LOBYTE(Priority) = RequestorMode;
              v29 = WofMungeDirectoryEnumerateWithoutShortnameFileIdAll(
                      (unsigned int)LowPart,
                      PoolWithTag,
                      Context,
                      v22,
                      v21,
                      Priority,
                      &v43);
            }
          }
          else
          {
            LOBYTE(Priority) = RequestorMode;
            v29 = WofMungeDirectoryEnumerateWithShortname(
                    (unsigned int)LowPart,
                    PoolWithTag,
                    Context,
                    v22,
                    v21,
                    Priority,
                    &v43);
          }
        }
        else
        {
          LOBYTE(Priority) = RequestorMode;
          v29 = WofMungeDirectoryEnumerateWithoutShortname(
                  (unsigned int)LowPart,
                  PoolWithTag,
                  Context,
                  v22,
                  v21,
                  Priority,
                  &v43);
        }
      }
      v19 = v29;
      goto LABEL_26;
    }
    FltReleaseContext(0);
  }
  return 1;
}

```

## disassembly

```asm
0x140036e20  push    rbp
0x140036e22  push    rbx
0x140036e23  push    rsi
0x140036e24  push    rdi
0x140036e25  push    r12
0x140036e27  push    r14
0x140036e29  push    r15
0x140036e2b  mov     rbp, rsp
0x140036e2e  sub     rsp, 70h
0x140036e32  mov     rax, [rcx+10h]
0x140036e36  xor     edi, edi
0x140036e38  mov     r15d, 1
0x140036e3e  mov     [rbp+RetNewCallbackData], rdi
0x140036e42  mov     ebx, r15d
0x140036e45  mov     [rbp+var_2C], edi
0x140036e48  mov     r12, rdx
0x140036e4b  mov     [rbp+Context], rdi
0x140036e4f  mov     rsi, rcx
0x140036e52  cmp     [rax+5], bl
0x140036e55  jnz     loc_1400370DA
0x140036e5b  mov     rcx, [r12+18h]; Instance
0x140036e60  lea     rdx, [rbp+Context]
0x140036e64  call    WofGetVolumeContext
0x140036e69  mov     r14d, eax
0x140036e6c  test    eax, eax
0x140036e6e  js      loc_140037131
0x140036e74  mov     rcx, [rbp+Context]; Context
0x140036e78  mov     eax, [rcx+38h]
0x140036e7b  test    bl, al
0x140036e7d  jnz     loc_140037125
0x140036e83  mov     [rsp+70h+arg_8], r13
0x140036e8b  mov     r15d, edi
0x140036e8e  call    cs:__imp_FltReleaseContext
0x140036e95  nop     dword ptr [rax+rax+00h]
0x140036e9a  mov     rdi, [rsi+10h]
0x140036e9e  mov     r13d, [rdi+28h]
0x140036ea2  cmp     r13d, 3Fh ; '?'
0x140036ea6  ja      loc_1400371CF
0x140036eac  mov     rcx, 900000600000000Eh
0x140036eb6  bt      rcx, r13
0x140036eba  jnb     loc_1400371CF
0x140036ec0  xor     r8d, r8d
0x140036ec3  lea     eax, [r13-1]; switch 81 cases
0x140036ec7  xor     edx, edx
0x140036ec9  xor     r14d, r14d
0x140036ecc  mov     ebx, 4
0x140036ed1  cmp     eax, 50h
0x140036ed4  jbe     loc_1400370EC
0x140036eda  mov     edi, [rdi+18h]; jumptable 0000000140037109 default case, cases 4-36,39-59,61,62,64-77
0x140036edd  add     edi, edx
0x140036edf  cmp     edi, edx
0x140036ee1  jb      loc_1400370A8
0x140036ee7  cmp     edi, r8d
0x140036eea  jb      loc_1400370A8
0x140036ef0  sub     edi, r8d
0x140036ef3  mov     eax, 10000h
0x140036ef8  cmp     edi, eax
0x140036efa  mov     ecx, 1; PoolType
0x140036eff  mov     r8d, 44666F57h; Tag
0x140036f05  cmova   edi, eax
0x140036f08  mov     edx, edi; NumberOfBytes
0x140036f0a  call    cs:__imp_ExAllocatePoolWithTag
0x140036f11  nop     dword ptr [rax+rax+00h]
0x140036f16  mov     r15, rax
0x140036f19  test    rax, rax
0x140036f1c  jz      loc_1400375A2
0x140036f22  mov     rdx, [r12+20h]; FileObject
0x140036f27  lea     r9, [rbp+RetNewCallbackData]; RetNewCallbackData
0x140036f2b  mov     rcx, [r12+18h]; Instance
0x140036f30  mov     r8d, 1; Flags
0x140036f36  call    cs:__imp_FltAllocateCallbackDataEx
0x140036f3d  nop     dword ptr [rax+rax+00h]
0x140036f42  test    eax, eax
0x140036f44  js      loc_1400375AE
0x140036f4a  mov     rdx, [rbp+RetNewCallbackData]
0x140036f4e  xor     r8d, r8d
0x140036f51  mov     rcx, rsi
0x140036f54  call    cs:__imp_FltPropagateIrpExtension
0x140036f5b  nop     dword ptr [rax+rax+00h]
0x140036f60  test    eax, eax
0x140036f62  js      loc_140037173
0x140036f68  mov     rax, [rbp+RetNewCallbackData]
0x140036f6c  mov     rcx, [rax+10h]
0x140036f70  mov     byte ptr [rcx+4], 0Ch
0x140036f74  mov     rax, [rbp+RetNewCallbackData]
0x140036f78  mov     rcx, [rax+10h]
0x140036f7c  mov     byte ptr [rcx+5], 1
0x140036f80  mov     rax, [rbp+RetNewCallbackData]
0x140036f84  mov     rcx, [rax+10h]
0x140036f88  mov     [rcx+18h], edi
0x140036f8b  mov     rax, [rbp+RetNewCallbackData]
0x140036f8f  mov     rcx, [rax+10h]
0x140036f93  mov     [rcx+28h], r14d
0x140036f97  mov     rax, [rbp+RetNewCallbackData]
0x140036f9b  mov     rdx, [rsi+10h]
0x140036f9f  mov     rcx, [rax+10h]
0x140036fa3  mov     rax, [rdx+20h]
0x140036fa7  mov     [rcx+20h], rax
0x140036fab  mov     rax, [rbp+RetNewCallbackData]
0x140036faf  mov     rdx, [rsi+10h]
0x140036fb3  mov     rcx, [rax+10h]
0x140036fb7  mov     eax, [rdx+30h]
0x140036fba  mov     [rcx+30h], eax
0x140036fbd  mov     rax, [rbp+RetNewCallbackData]
0x140036fc1  mov     rcx, [rax+10h]
0x140036fc5  mov     [rcx+38h], r15
0x140036fc9  mov     rax, [rbp+RetNewCallbackData]
0x140036fcd  mov     rcx, [rax+10h]
0x140036fd1  mov     qword ptr [rcx+40h], 0
0x140036fd9  mov     rax, [rbp+RetNewCallbackData]
0x140036fdd  mov     rdx, [rsi+10h]
0x140036fe1  mov     rcx, [rax+10h]
0x140036fe5  movzx   eax, byte ptr [rdx+6]
0x140036fe9  mov     [rcx+6], al
0x140036fec  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x140036ff0  call    cs:__imp_FltPerformSynchronousIo
0x140036ff7  nop     dword ptr [rax+rax+00h]
0x140036ffc  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x140037000  mov     eax, [rcx+20h]
0x140037003  mov     edi, [rcx+18h]
0x140037006  mov     dword ptr [rbp+Context], eax
0x140037009  call    cs:__imp_FltFreeCallbackData
0x140037010  nop     dword ptr [rax+rax+00h]
0x140037015  xor     r12d, r12d
0x140037018  mov     [rbp+RetNewCallbackData], 0
0x140037020  cmp     edi, 80000005h
0x140037026  mov     [rsi+18h], edi
0x140037029  cmovnz  r12d, edi
0x14003702d  test    r12d, r12d
0x140037030  js      loc_1400370C1
0x140037036  mov     rax, [rsi+10h]
0x14003703a  cmp     qword ptr [rax+40h], 0
0x14003703f  mov     edi, [rax+18h]
0x140037042  jnz     loc_1400375B6
0x140037048  mov     r9, [rax+38h]
0x14003704c  mov     eax, [rsi]
0x14003704e  test    al, 8
0x140037050  jnz     loc_14003716C
0x140037056  movzx   ecx, byte ptr [rsi+50h]
0x14003705a  cmp     r14d, 4Fh ; 'O'
0x14003705e  jz      loc_140037144
0x140037064  sub     r14d, 3Ch ; '<'
0x140037068  jz      loc_140037647
0x14003706e  sub     r14d, 3
0x140037072  jz      loc_140037622
0x140037078  sub     r14d, 0Fh
0x14003707c  jz      loc_1400371A7
0x140037082  sub     r14d, 2
0x140037086  jz      loc_1400375FD
0x14003708c  cmp     r14d, 1
0x140037090  jz      loc_1400375D8
0x140037096  test    r12d, r12d
0x140037099  js      loc_14003766C
0x14003709f  mov     eax, [rbp+var_2C]
0x1400370a2  mov     [rsi+20h], rax
0x1400370a6  jmp     short loc_1400370AF
0x1400370a8  mov     dword ptr [rsi+18h], 0C000000Dh
0x1400370af  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x1400370b3  test    rcx, rcx
0x1400370b6  jnz     loc_140037675
0x1400370bc  test    r15, r15
0x1400370bf  jz      short loc_1400370D2
0x1400370c1  xor     edx, edx; Tag
0x1400370c3  mov     rcx, r15; P
0x1400370c6  call    cs:__imp_ExFreePoolWithTag
0x1400370cd  nop     dword ptr [rax+rax+00h]
0x1400370d2  mov     r13, [rsp+70h+arg_8]
0x1400370da  mov     eax, ebx
0x1400370dc  add     rsp, 70h
0x1400370e0  pop     r15
0x1400370e2  pop     r14
0x1400370e4  pop     r12
0x1400370e6  pop     rdi
0x1400370e7  pop     rsi
0x1400370e8  pop     rbx
0x1400370e9  pop     rbp
0x1400370ea  retn
0x1400370ec  lea     r9, cs:140000000h
0x1400370f3  cdqe
0x1400370f5  movzx   eax, ds:(byte_1400144AC - 140000000h)[r9+rax]
0x1400370fe  mov     ecx, ds:(jpt_140037109 - 140000000h)[r9+rax*4]
0x140037106  add     rcx, r9
0x140037109  jmp     rcx; switch jump
0x14003710f  mov     edx, 6Ah ; 'j'; jumptable 0000000140037109 case 3
0x140037114  mov     r8d, 5Eh ; '^'
0x14003711a  mov     r14d, 4Fh ; 'O'
0x140037120  jmp     def_140037109; jumptable 0000000140037109 default case, cases 4-36,39-59,61,62,64-77
0x140037125  call    cs:__imp_FltReleaseContext
0x14003712c  nop     dword ptr [rax+rax+00h]
0x140037131  mov     eax, r15d
0x140037134  add     rsp, 70h
0x140037138  pop     r15
0x14003713a  pop     r14
0x14003713c  pop     r12
0x14003713e  pop     rdi
0x14003713f  pop     rsi
0x140037140  pop     rbx
0x140037141  pop     rbp
0x140037142  retn
0x140037144  mov     r8d, dword ptr [rbp+Context]
0x140037148  lea     rax, [rbp+var_2C]
0x14003714c  mov     [rsp+70h+var_40], rax
0x140037151  mov     rdx, r15
0x140037154  mov     byte ptr [rsp+70h+Priority], cl
0x140037158  mov     ecx, r13d
0x14003715b  mov     [rsp+70h+BugCheckOnFailure], edi
0x14003715f  call    WofMungeDirectoryEnumerateWithShortnameFileId64
0x140037164  mov     r12d, eax
0x140037167  jmp     loc_140037096
0x14003716c  xor     cl, cl
0x14003716e  jmp     loc_14003705A
0x140037173  mov     [rsi+18h], eax
0x140037176  jmp     loc_1400370AF
0x14003717b  mov     edx, 50h ; 'P'; jumptable 0000000140037109 case 2
0x140037180  mov     r8d, 44h ; 'D'
0x140037186  mov     r14d, 4Eh ; 'N'
0x14003718c  jmp     def_140037109; jumptable 0000000140037109 default case, cases 4-36,39-59,61,62,64-77
0x140037191  mov     edx, 6Ah ; 'j'; jumptable 0000000140037109 case 37
0x140037196  mov     r8d, 68h ; 'h'
0x14003719c  mov     r14d, 4Fh ; 'O'
0x1400371a2  jmp     def_140037109; jumptable 0000000140037109 default case, cases 4-36,39-59,61,62,64-77
0x1400371a7  mov     r8d, dword ptr [rbp+Context]
0x1400371ab  lea     rax, [rbp+var_2C]
0x1400371af  mov     [rsp+70h+var_40], rax
0x1400371b4  mov     rdx, r15
0x1400371b7  mov     byte ptr [rsp+70h+Priority], cl
0x1400371bb  mov     ecx, r13d
0x1400371be  mov     [rsp+70h+BugCheckOnFailure], edi
0x1400371c2  call    WofMungeDirectoryEnumerateWithoutShortnameFileId64
0x1400371c7  mov     r12d, eax
0x1400371ca  jmp     loc_140037096
0x1400371cf  lea     eax, [r13-4Eh]
0x1400371d3  cmp     eax, 3
0x1400371d6  jbe     loc_140036EC0
0x1400371dc  cmp     r13d, 21h ; '!'
0x1400371e0  jnz     loc_1400370AF
0x1400371e6  cmp     cs:byte_140018454, r15b
0x1400371ed  jz      loc_1400370AF
0x1400371f3  mov     ebx, 4
0x1400371f8  movzx   edx, byte ptr [rdi+6]
0x1400371fc  mov     eax, [rdi+18h]
0x1400371ff  mov     [rbp+arg_18], dl
0x140037202  mov     [rbp+var_28], eax
0x140037205  cmp     [rdi+40h], r15
0x140037209  jz      loc_1400372D4
0x14003720f  mov     rcx, rsi; CallbackData
0x140037212  call    cs:__imp_FltLockUserBuffer
0x140037219  nop     dword ptr [rax+rax+00h]
0x14003721e  mov     r14d, eax
0x140037221  test    eax, eax
0x140037223  jns     short loc_14003722D
0x140037225  mov     [rsi+18h], eax
0x140037228  jmp     loc_1400370AF
0x14003722d  mov     rax, [rsi+10h]
0x140037231  mov     rcx, [rax+40h]; MemoryDescriptorList
0x140037235  test    byte ptr [rcx+0Ah], 5
0x140037239  jz      short loc_140037258
0x14003723b  mov     r13, [rcx+18h]
0x14003723f  mov     [rbp+var_10], r13
0x140037243  test    r13, r13
0x140037246  jnz     loc_1400372EB
0x14003724c  mov     dword ptr [rsi+18h], 0C0000017h
0x140037253  jmp     loc_1400370AF
0x140037258  mov     [rsp+70h+Priority], 40000010h; Priority
0x140037260  xor     r9d, r9d; RequestedAddress
0x140037263  xor     edx, edx; AccessMode
0x140037265  mov     [rsp+70h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x14003726a  mov     r8d, 1; CacheType
0x140037270  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140037277  nop     dword ptr [rax+rax+00h]
0x14003727c  mov     r13, rax
0x14003727f  jmp     short loc_14003723F
0x140037281  mov     rax, [rsi+10h]
0x140037285  mov     rcx, [rax+40h]; MemoryDescriptorList
0x140037289  test    byte ptr [rcx+0Ah], 5
0x14003728d  jz      short loc_1400372A8
0x14003728f  mov     r9, [rcx+18h]
0x140037293  test    r9, r9
0x140037296  jnz     loc_14003716C
0x14003729c  mov     dword ptr [rsi+18h], 0C0000017h
0x1400372a3  jmp     loc_1400370AF
0x1400372a8  mov     [rsp+70h+Priority], 40000010h; Priority
0x1400372b0  xor     r9d, r9d; RequestedAddress
0x1400372b3  xor     edx, edx; AccessMode
0x1400372b5  mov     [rsp+70h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400372bd  mov     r8d, 1; CacheType
0x1400372c3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400372ca  nop     dword ptr [rax+rax+00h]
0x1400372cf  mov     r9, rax
0x1400372d2  jmp     short loc_140037293
0x1400372d4  mov     rax, [rdi+38h]
0x1400372d8  mov     [rbp+var_10], rax
0x1400372dc  mov     eax, [rsi]
0x1400372de  test    al, 8
0x1400372e0  jnz     short loc_1400372EB
0x1400372e2  movzx   eax, byte ptr [rsi+50h]
0x1400372e6  mov     byte ptr [rbp+Context], al
0x1400372e9  jmp     short loc_1400372EF
0x1400372eb  mov     byte ptr [rbp+Context], r15b
0x1400372ef  mov     ecx, [rdi+18h]
  ... truncated ...
```
