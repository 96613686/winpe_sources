# VmReadWrite

- ea: `0x1400015a0`
- end: `0x1400018d7`
- name: `VmReadWrite`
- size: `823`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400015a0`
- `0x140002910`
- `0x140005090`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400016fc`
- `ntoskrnl!IofCallDriver` at `0x1400016fc`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140001743`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140001743`
- `ntoskrnl!IofCompleteRequest` at `0x14000176f`
- `ntoskrnl!IofCompleteRequest` at `0x140001793`
- `ntoskrnl!IofCompleteRequest` at `0x14000184a`
- `ntoskrnl!IofCompleteRequest` at `0x14000176f`
- `ntoskrnl!IofCompleteRequest` at `0x140001793`
- `ntoskrnl!IofCompleteRequest` at `0x14000184a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140001753`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400017ea`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140001801`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000182e`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140001753`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400017ea`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140001801`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000182e`

## pseudocode

```c
__int64 __fastcall VmReadWrite(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  PVOID DeviceExtension; // rbx
  NTSTATUS v5; // ebp
  char v6; // cl
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *p_CurrentStackLocation; // r15
  __int64 v8; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v10; // rax
  struct _IO_STACK_LOCATION *v11; // rax
  unsigned int v12; // edx
  __int64 v14; // rax

  DeviceExtension = DeviceObject->DeviceExtension;
  if ( *((_DWORD *)DeviceExtension + 4) != 1 )
  {
    v5 = -1073741810;
    Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = -1073741810;
LABEL_26:
    IofCompleteRequest(Irp, 0);
    return (unsigned int)v5;
  }
  if ( Irp )
    Irp->IoStatus.Information = 0;
  v5 = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)DeviceExtension, Irp);
  if ( v5 == 259 )
    return 259;
  if ( *((_BYTE *)DeviceExtension + 426) )
  {
    if ( *((_QWORD *)DeviceExtension + 54) )
      goto LABEL_7;
LABEL_29:
    v6 = 0;
    goto LABEL_8;
  }
  if ( !*((_QWORD *)DeviceExtension + 43) )
    goto LABEL_29;
LABEL_7:
  v6 = 1;
LABEL_8:
  if ( !*((_BYTE *)DeviceExtension + 156) || !v6 )
  {
    ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 14));
    v5 = -1073741810;
    goto LABEL_32;
  }
  if ( *((_BYTE *)DeviceExtension + 160) )
  {
    ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 14));
    v5 = -2147483632;
    goto LABEL_32;
  }
  if ( v5 < 0 )
  {
LABEL_32:
    Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = v5;
    goto LABEL_26;
  }
  p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&Irp->Tail.Overlay.CurrentStackLocation;
  if ( _bittest64((const signed __int64 *)DeviceExtension + 39, 0x3Cu)
    && p_CurrentStackLocation->CurrentStackLocation->MajorFunction == 4 )
  {
    ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 14));
    Irp->IoStatus.Status = -1073741808;
    Irp->IoStatus.Information = 0;
    IofCompleteRequest(Irp, 0);
    return 3221225488LL;
  }
  else
  {
    v8 = *((_QWORD *)DeviceExtension + 43);
    if ( v8 && (*(_DWORD *)(v8 + 48) & 2) != 0 )
    {
      DeviceObject->Flags |= 2u;
      *(_DWORD *)(*((_QWORD *)DeviceExtension + 43) + 48LL) &= ~2u;
    }
    if ( (DeviceObject->Flags & 2) == 0 || (p_CurrentStackLocation->CurrentStackLocation->Flags & 2) != 0 )
    {
      CurrentStackLocation = p_CurrentStackLocation->CurrentStackLocation;
      *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&p_CurrentStackLocation->CurrentStackLocation->MajorFunction;
      *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                                 + 6);
      CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
      CurrentStackLocation[-1].Control = 0;
      v10 = p_CurrentStackLocation->CurrentStackLocation;
      v10[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)VmpReadWriteCompletionRoutine;
      v10[-1].Context = DeviceExtension;
      v10[-1].Control = -32;
      if ( *((_BYTE *)DeviceExtension + 161) )
        (*(void (__fastcall **)(_QWORD, LARGE_INTEGER *, PUNICODE_STRING *))(*((_QWORD *)DeviceExtension + 1) + 320LL))(
          *((_QWORD *)DeviceExtension + 28),
          &p_CurrentStackLocation->CurrentStackLocation->Parameters.Read.ByteOffset,
          &p_CurrentStackLocation->CurrentStackLocation->Parameters.QueryDirectory.FileName);
      else
        p_CurrentStackLocation->CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart = 0;
      v11 = p_CurrentStackLocation->CurrentStackLocation;
      if ( *((_BYTE *)DeviceExtension + 426) )
      {
        --Irp->CurrentLocation;
        p_CurrentStackLocation->CurrentStackLocation = v11 - 1;
        return (*(unsigned int (__fastcall **)(_QWORD, PIRP))(*(_QWORD *)(*((_QWORD *)DeviceExtension + 1) + 392LL)
                                                            + 112LL))(
                 *((_QWORD *)DeviceExtension + 54),
                 Irp);
      }
      else
      {
        v11[-1].Flags |= 0x10u;
        v12 = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 43), Irp);
        if ( v12 == -2147483626 )
        {
          v14 = *((_QWORD *)DeviceExtension + 43);
          if ( v14 )
          {
            if ( (*(_DWORD *)(v14 + 48) & 2) != 0 )
            {
              DeviceObject->Flags |= 2u;
              *(_DWORD *)(*((_QWORD *)DeviceExtension + 43) + 48LL) &= ~2u;
            }
          }
        }
      }
      return v12;
    }
    else
    {
      IoSetHardErrorOrVerifyDevice(Irp, DeviceObject);
      ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 14));
      Irp->IoStatus.Status = -2147483626;
      Irp->IoStatus.Information = 0;
      IofCompleteRequest(Irp, 0);
      return 2147483670LL;
    }
  }
}

```

## disassembly

```asm
0x1400015a0  mov     [rsp+arg_8], rbx
0x1400015a5  mov     [rsp+arg_10], rbp
0x1400015aa  push    rsi
0x1400015ab  push    rdi
0x1400015ac  push    r14
0x1400015ae  sub     rsp, 20h
0x1400015b2  mov     rbx, [rcx+40h]
0x1400015b6  xor     r14d, r14d
0x1400015b9  mov     rdi, rdx
0x1400015bc  mov     rsi, rcx
0x1400015bf  cmp     dword ptr [rbx+10h], 1
0x1400015c3  jnz     loc_140001782
0x1400015c9  test    rdx, rdx
0x1400015cc  jz      short loc_1400015D2
0x1400015ce  mov     [rdx+38h], r14
0x1400015d2  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x1400015d5  call    ?VmpAcquireRundownShared@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpAcquireRundownShared(VM_VOLUME_EXTENSION *,_IRP *)
0x1400015da  mov     ebp, eax
0x1400015dc  cmp     eax, 103h
0x1400015e1  jz      loc_1400018CD
0x1400015e7  cmp     [rbx+1AAh], r14b
0x1400015ee  jnz     loc_1400017D2
0x1400015f4  cmp     [rbx+158h], r14
0x1400015fb  jz      loc_1400017DF
0x140001601  mov     cl, 1
0x140001603  movzx   eax, byte ptr [rbx+9Ch]
0x14000160a  test    al, al
0x14000160c  jz      loc_1400017E6
0x140001612  test    cl, cl
0x140001614  jz      loc_1400017E6
0x14000161a  cmp     [rbx+0A0h], r14b
0x140001621  jnz     loc_1400017FD
0x140001627  test    ebp, ebp
0x140001629  js      loc_140001812
0x14000162f  bt      qword ptr [rbx+138h], 3Ch ; '<'
0x140001638  mov     [rsp+38h+arg_0], r15
0x14000163d  lea     r15, [rdi+0B8h]
0x140001644  jb      loc_14000181E
0x14000164a  mov     rax, [rbx+158h]
0x140001651  test    rax, rax
0x140001654  jz      short loc_140001661
0x140001656  mov     eax, [rax+30h]
0x140001659  test    al, 2
0x14000165b  jnz     loc_140001860
0x140001661  mov     eax, [rsi+30h]
0x140001664  test    al, 2
0x140001666  jnz     loc_140001730
0x14000166c  mov     rax, [r15]
0x14000166f  lea     rcx, VmpReadWriteCompletionRoutine
0x140001676  movups  xmm0, xmmword ptr [rax]
0x140001679  movups  xmmword ptr [rax-48h], xmm0
0x14000167d  movups  xmm1, xmmword ptr [rax+10h]
0x140001681  movups  xmmword ptr [rax-38h], xmm1
0x140001685  movups  xmm0, xmmword ptr [rax+20h]
0x140001689  movups  xmmword ptr [rax-28h], xmm0
0x14000168d  movsd   xmm1, qword ptr [rax+30h]
0x140001692  movsd   qword ptr [rax-18h], xmm1
0x140001697  mov     [rax-45h], r14b
0x14000169b  mov     rax, [r15]
0x14000169e  mov     [rax-10h], rcx
0x1400016a2  mov     [rax-8], rbx
0x1400016a6  mov     byte ptr [rax-45h], 0E0h
0x1400016aa  mov     r8, [r15]
0x1400016ad  movzx   eax, byte ptr [rbx+0A1h]
0x1400016b4  lea     rcx, [r8+18h]
0x1400016b8  test    al, al
0x1400016ba  jz      loc_140001885
0x1400016c0  mov     rax, [rbx+8]
0x1400016c4  mov     rdx, rcx
0x1400016c7  mov     rcx, [rbx+0E0h]
0x1400016ce  add     r8, 10h
0x1400016d2  mov     rax, [rax+140h]
0x1400016d9  call    _guard_dispatch_icall
0x1400016de  mov     rdx, rdi; Irp
0x1400016e1  mov     rax, [r15]
0x1400016e4  cmp     [rbx+1AAh], r14b
0x1400016eb  jnz     loc_1400017A6
0x1400016f1  or      byte ptr [rax-46h], 10h
0x1400016f5  mov     rcx, [rbx+158h]; DeviceObject
0x1400016fc  call    cs:__imp_IofCallDriver
0x140001703  nop     dword ptr [rax+rax+00h]
0x140001708  mov     edx, eax
0x14000170a  cmp     eax, 80000016h
0x14000170f  jz      loc_14000188D
0x140001715  mov     eax, edx
0x140001717  mov     r15, [rsp+38h+arg_0]
0x14000171c  mov     rbx, [rsp+38h+arg_8]
0x140001721  mov     rbp, [rsp+38h+arg_10]
0x140001726  add     rsp, 20h
0x14000172a  pop     r14
0x14000172c  pop     rdi
0x14000172d  pop     rsi
0x14000172e  retn
0x140001730  mov     rax, [r15]
0x140001733  test    byte ptr [rax+2], 2
0x140001737  jnz     loc_14000166C
0x14000173d  mov     rdx, rsi; DeviceObject
0x140001740  mov     rcx, rdi; Irp
0x140001743  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x14000174a  nop     dword ptr [rax+rax+00h]
0x14000174f  mov     rcx, [rbx+70h]; RunRefCacheAware
0x140001753  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14000175a  nop     dword ptr [rax+rax+00h]
0x14000175f  xor     edx, edx; PriorityBoost
0x140001761  mov     dword ptr [rdi+30h], 80000016h
0x140001768  mov     rcx, rdi; Irp
0x14000176b  mov     [rdi+38h], r14
0x14000176f  call    cs:__imp_IofCompleteRequest
0x140001776  nop     dword ptr [rax+rax+00h]
0x14000177b  mov     eax, 80000016h
0x140001780  jmp     short loc_140001717
0x140001782  mov     ebp, 0C000000Eh
0x140001787  mov     [rdx+38h], r14
0x14000178b  mov     [rdx+30h], ebp
0x14000178e  xor     edx, edx; PriorityBoost
0x140001790  mov     rcx, rdi; Irp
0x140001793  call    cs:__imp_IofCompleteRequest
0x14000179a  nop     dword ptr [rax+rax+00h]
0x14000179f  mov     eax, ebp
0x1400017a1  jmp     loc_14000171C
0x1400017a6  dec     byte ptr [rdi+43h]
0x1400017a9  add     rax, 0FFFFFFFFFFFFFFB8h
0x1400017ad  mov     [r15], rax
0x1400017b0  mov     rax, [rbx+8]
0x1400017b4  mov     rcx, [rax+188h]
0x1400017bb  mov     rax, [rcx+70h]
0x1400017bf  mov     rcx, [rbx+1B0h]
0x1400017c6  call    _guard_dispatch_icall
0x1400017cb  mov     edx, eax
0x1400017cd  jmp     loc_140001715
0x1400017d2  cmp     [rbx+1B0h], r14
0x1400017d9  jnz     loc_140001601
0x1400017df  xor     cl, cl
0x1400017e1  jmp     loc_140001603
0x1400017e6  mov     rcx, [rbx+70h]; RunRefCacheAware
0x1400017ea  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400017f1  nop     dword ptr [rax+rax+00h]
0x1400017f6  mov     ebp, 0C000000Eh
0x1400017fb  jmp     short loc_140001812
0x1400017fd  mov     rcx, [rbx+70h]; RunRefCacheAware
0x140001801  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140001808  nop     dword ptr [rax+rax+00h]
0x14000180d  mov     ebp, 80000010h
0x140001812  mov     [rdi+38h], r14
0x140001816  mov     [rdi+30h], ebp
0x140001819  jmp     loc_14000178E
0x14000181e  mov     rax, [r15]
0x140001821  cmp     byte ptr [rax], 4
0x140001824  jnz     loc_14000164A
0x14000182a  mov     rcx, [rbx+70h]; RunRefCacheAware
0x14000182e  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140001835  nop     dword ptr [rax+rax+00h]
0x14000183a  xor     edx, edx; PriorityBoost
0x14000183c  mov     dword ptr [rdi+30h], 0C0000010h
0x140001843  mov     rcx, rdi; Irp
0x140001846  mov     [rdi+38h], r14
0x14000184a  call    cs:__imp_IofCompleteRequest
0x140001851  nop     dword ptr [rax+rax+00h]
0x140001856  mov     eax, 0C0000010h
0x14000185b  jmp     loc_140001717
0x140001860  mov     eax, [rsi+30h]
0x140001863  or      eax, 2
0x140001866  mov     [rsi+30h], eax
0x140001869  mov     rax, [rbx+158h]
0x140001870  mov     ecx, [rax+30h]
0x140001873  mov     rax, [rbx+158h]
0x14000187a  and     ecx, 0FFFFFFFDh
0x14000187d  mov     [rax+30h], ecx
0x140001880  jmp     loc_140001661
0x140001885  mov     [rcx], r14
0x140001888  jmp     loc_1400016DE
0x14000188d  mov     rax, [rbx+158h]
0x140001894  test    rax, rax
0x140001897  jz      loc_140001715
0x14000189d  mov     eax, [rax+30h]
0x1400018a0  test    al, 2
0x1400018a2  jz      loc_140001715
0x1400018a8  mov     eax, [rsi+30h]
0x1400018ab  or      eax, 2
0x1400018ae  mov     [rsi+30h], eax
0x1400018b1  mov     rax, [rbx+158h]
0x1400018b8  mov     ecx, [rax+30h]
0x1400018bb  mov     rax, [rbx+158h]
0x1400018c2  and     ecx, 0FFFFFFFDh
0x1400018c5  mov     [rax+30h], ecx
0x1400018c8  jmp     loc_140001715
0x1400018cd  mov     eax, 103h
0x1400018d2  jmp     loc_14000171C
```
