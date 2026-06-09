# SpControlPnp(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140033590`
- end: `0x140033835`
- name: `?SpControlPnp@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `677`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, PIRP Irp)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x14001f2a0`
- `0x1400268c0`
- `0x140031db8`
- `0x140033590`
- `0x1400a1bd8`
- `0x1400a3d48`
- `0x1400a6e28`
- `0x1400a7330`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400336c4`
- `ntoskrnl!ObfReferenceObject` at `0x1400336c4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140033624`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140033624`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140033679`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400336e7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140033679`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400336e7`
- `ntoskrnl!IoDeleteDevice` at `0x1400337a8`
- `ntoskrnl!IoDeleteDevice` at `0x1400337a8`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140033706`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14003372c`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400337c0`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140033706`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14003372c`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400337c0`
- `ntoskrnl!IofCompleteRequest` at `0x1400337fe`
- `ntoskrnl!IofCompleteRequest` at `0x1400337fe`

## pseudocode

```c
__int64 __fastcall SpControlPnp(struct _DEVICE_OBJECT *a1, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  SP_CONTROL *v4; // rbp
  PIRP v5; // rbx
  unsigned int MinorFunction; // r8d
  struct _DEVICE_OBJECT *v7; // rcx
  unsigned int v8; // r8d
  unsigned int v9; // r8d
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  char *v12; // r12
  int v13; // edx
  __int64 *v14; // rbp
  __int64 *i; // rcx
  _DWORD *v16; // r15
  int Status; // edi
  __int64 *v18; // rdi
  __int64 v19; // r14
  char v20; // al
  void *v21; // rcx
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  unsigned int v24; // r8d
  unsigned int v25; // r8d
  unsigned int v26; // r8d
  int RootId; // eax

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v4 = (SP_CONTROL *)((char *)a1->DeviceExtension + 8);
  v5 = Irp;
  MinorFunction = CurrentStackLocation->MinorFunction;
  v7 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1->DeviceExtension + 3);
  if ( MinorFunction <= 9 )
  {
    if ( MinorFunction == 9 )
    {
      IoForwardIrpSynchronously(v7, Irp);
      *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 4) |= 0xC0u;
      Status = v5->IoStatus.Status;
    }
    else
    {
      if ( CurrentStackLocation->MinorFunction )
      {
        v8 = MinorFunction - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            v10 = v9 - 1;
            if ( v10 )
            {
              v11 = v10 - 3;
              if ( v11 )
              {
                if ( v11 != 1 || CurrentStackLocation->Parameters.Read.Length )
                  return SpControlSkip(a1, Irp);
                v12 = (char *)v4 + 320;
                ExAcquirePushLockExclusiveEx((char *)v4 + 320, 0);
                v13 = 0;
                v14 = (__int64 *)((char *)v4 + 304);
                for ( i = (__int64 *)*v14; i != v14; i = (__int64 *)*i )
                {
                  if ( (unsigned __int8)(*((_BYTE *)i + 160) - 1) <= 2u )
                    ++v13;
                }
                v16 = SC_ENV::Allocate((unsigned int)(8 * v13 + 8), 0x58587053u, 0, 0);
                if ( !v16 )
                {
                  ExReleasePushLockExclusiveEx(v12, 0);
                  Status = -1073741670;
                  v5->IoStatus.Information = 0;
                  goto LABEL_43;
                }
                v18 = (__int64 *)*v14;
                v19 = 0;
                while ( v18 != v14 )
                {
                  v20 = *((_BYTE *)v18 + 160);
                  if ( v20 == 4 )
                  {
                    *((_BYTE *)v18 + 160) = 5;
                  }
                  else if ( (unsigned __int8)(v20 - 2) <= 1u )
                  {
                    v21 = (void *)v18[19];
                    *(_QWORD *)&v16[2 * v19 + 2] = v21;
                    v19 = (unsigned int)(v19 + 1);
                    ObfReferenceObject(v21);
                    *((_BYTE *)v18 + 160) = 3;
                  }
                  v18 = (__int64 *)*v18;
                }
                *v16 = v19;
                ExReleasePushLockExclusiveEx(v12, 0);
                v5->IoStatus.Information = (ULONG_PTR)v16;
                goto LABEL_25;
              }
            }
LABEL_47:
            Irp->IoStatus.Status = 0;
            return SpControlSkip(a1, Irp);
          }
LABEL_36:
          SP_CONTROL::Remove(v4);
          if ( CurrentStackLocation->MinorFunction == 2 )
          {
            SP_CONTROL::~SP_CONTROL(v4);
            WPP_MAIN_CB.DeviceExtension = 0;
            SP_QOS_CONTEXT::UnInitializeLimiterInternal();
            IoDeleteDevice(a1);
          }
LABEL_25:
          v5->IoStatus.Status = 0;
          goto LABEL_26;
        }
        goto LABEL_38;
      }
      IoForwardIrpSynchronously(v7, Irp);
      Status = v5->IoStatus.Status;
      if ( Status >= 0 )
        Status = SP_CONTROL::Start(v4);
    }
    goto LABEL_42;
  }
  v22 = MinorFunction - 10;
  if ( !v22 )
    goto LABEL_47;
  v23 = v22 - 1;
  if ( !v23 )
    goto LABEL_47;
  v24 = v23 - 8;
  if ( v24 )
  {
    v25 = v24 - 1;
    if ( !v25 )
    {
      IoForwardIrpSynchronously(v7, Irp);
      Status = 0;
      v5->IoStatus.Information = 32;
      goto LABEL_43;
    }
    v26 = v25 - 2;
    if ( v26 )
    {
      if ( v26 != 1 )
        return SpControlSkip(a1, Irp);
      goto LABEL_36;
    }
LABEL_38:
    Status = -1073741808;
    goto LABEL_43;
  }
  RootId = SpQueryRootId((struct SP_CONTROL *)v7, Irp);
  Status = RootId;
  if ( RootId >= 0 )
  {
    v5->IoStatus.Status = RootId;
    goto LABEL_26;
  }
  if ( RootId != -1073741637 )
  {
LABEL_42:
    if ( Status == -1073741637 )
    {
      Status = v5->IoStatus.Status;
      goto LABEL_45;
    }
LABEL_43:
    v5->IoStatus.Status = Status;
LABEL_45:
    IofCompleteRequest(v5, 0);
    return (unsigned int)Status;
  }
LABEL_26:
  Irp = v5;
  return SpControlSkip(a1, Irp);
}

```

## disassembly

```asm
0x140033590  push    rbx
0x140033592  push    rbp
0x140033593  push    rsi
0x140033594  push    rdi
0x140033595  push    r12
0x140033597  push    r14
0x140033599  push    r15
0x14003359b  sub     rsp, 20h
0x14003359f  mov     rbp, [rcx+40h]
0x1400335a3  mov     rsi, rcx
0x1400335a6  mov     rdi, [rdx+0B8h]
0x1400335ad  add     rbp, 8
0x1400335b1  mov     rbx, rdx
0x1400335b4  mov     r14d, 0C00000BBh
0x1400335ba  movzx   r8d, byte ptr [rdi+1]
0x1400335bf  mov     rcx, [rbp+10h]; struct SP_CONTROL *
0x1400335c3  cmp     r8d, 9
0x1400335c7  ja      loc_14003374B
0x1400335cd  jz      loc_14003372C
0x1400335d3  test    r8d, r8d
0x1400335d6  jz      loc_140033706
0x1400335dc  sub     r8d, 1
0x1400335e0  jz      loc_1400337B9
0x1400335e6  sub     r8d, 1
0x1400335ea  jz      loc_14003377B
0x1400335f0  sub     r8d, 1
0x1400335f4  jz      loc_140033816
0x1400335fa  sub     r8d, 3
0x1400335fe  jz      loc_140033816
0x140033604  cmp     r8d, 1
0x140033608  jnz     loc_14003381D
0x14003360e  cmp     dword ptr [rdi+8], 0
0x140033612  jnz     loc_14003381D
0x140033618  lea     r12, [rbp+140h]
0x14003361f  xor     edx, edx
0x140033621  mov     rcx, r12
0x140033624  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003362b  nop     dword ptr [rax+rax+00h]
0x140033630  xor     edx, edx
0x140033632  add     rbp, 130h
0x140033639  mov     rcx, [rbp+0]
0x14003363d  jmp     short loc_140033650
0x14003363f  mov     al, [rcx+0A0h]
0x140033645  dec     al
0x140033647  cmp     al, 2
0x140033649  ja      short loc_14003364D
0x14003364b  inc     edx
0x14003364d  mov     rcx, [rcx]
0x140033650  cmp     rcx, rbp
0x140033653  jnz     short loc_14003363F
0x140033655  lea     ecx, ds:8[rdx*8]; unsigned __int64
0x14003365c  xor     r9d, r9d; unsigned int
0x14003365f  mov     edx, 58587053h; unsigned int
0x140033664  xor     r8d, r8d; unsigned __int8
0x140033667  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14003366c  mov     r15, rax
0x14003366f  test    rax, rax
0x140033672  jnz     short loc_140033693
0x140033674  xor     edx, edx
0x140033676  mov     rcx, r12
0x140033679  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140033680  nop     dword ptr [rax+rax+00h]
0x140033685  mov     edi, 0C000009Ah
0x14003368a  mov     [rbx+38h], r15
0x14003368e  jmp     loc_1400337F1
0x140033693  mov     rdi, [rbp+0]
0x140033697  xor     r14d, r14d
0x14003369a  jmp     short loc_1400336DA
0x14003369c  mov     al, [rdi+0A0h]
0x1400336a2  cmp     al, 4
0x1400336a4  jnz     short loc_1400336AF
0x1400336a6  mov     byte ptr [rdi+0A0h], 5
0x1400336ad  jmp     short loc_1400336D7
0x1400336af  sub     al, 2
0x1400336b1  cmp     al, 1
0x1400336b3  ja      short loc_1400336D7
0x1400336b5  mov     rcx, [rdi+98h]; Object
0x1400336bc  mov     [r15+r14*8+8], rcx
0x1400336c1  inc     r14d
0x1400336c4  call    cs:__imp_ObfReferenceObject
0x1400336cb  nop     dword ptr [rax+rax+00h]
0x1400336d0  mov     byte ptr [rdi+0A0h], 3
0x1400336d7  mov     rdi, [rdi]
0x1400336da  cmp     rdi, rbp
0x1400336dd  jnz     short loc_14003369C
0x1400336df  xor     edx, edx
0x1400336e1  mov     [r15], r14d
0x1400336e4  mov     rcx, r12
0x1400336e7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400336ee  nop     dword ptr [rax+rax+00h]
0x1400336f3  mov     [rbx+38h], r15
0x1400336f7  mov     dword ptr [rbx+30h], 0
0x1400336fe  mov     rdx, rbx; Irp
0x140033701  jmp     loc_14003381D
0x140033706  call    cs:__imp_IoForwardIrpSynchronously
0x14003370d  nop     dword ptr [rax+rax+00h]
0x140033712  mov     edi, [rbx+30h]
0x140033715  test    edi, edi
0x140033717  js      loc_1400337EC
0x14003371d  mov     rcx, rbp; this
0x140033720  call    ?Start@SP_CONTROL@@QEAAJXZ; SP_CONTROL::Start(void)
0x140033725  mov     edi, eax
0x140033727  jmp     loc_1400337EC
0x14003372c  call    cs:__imp_IoForwardIrpSynchronously
0x140033733  nop     dword ptr [rax+rax+00h]
0x140033738  mov     rax, [rdi+8]
0x14003373c  or      dword ptr [rax+4], 0C0h
0x140033743  mov     edi, [rbx+30h]
0x140033746  jmp     loc_1400337EC
0x14003374b  sub     r8d, 0Ah
0x14003374f  jz      loc_140033816
0x140033755  sub     r8d, 1
0x140033759  jz      loc_140033816
0x14003375f  sub     r8d, 8
0x140033763  jz      short loc_1400337D8
0x140033765  sub     r8d, 1
0x140033769  jz      short loc_1400337C0
0x14003376b  sub     r8d, 2
0x14003376f  jz      short loc_1400337B9
0x140033771  cmp     r8d, 1
0x140033775  jnz     loc_14003381D
0x14003377b  mov     rcx, rbp; this
0x14003377e  call    ?Remove@SP_CONTROL@@QEAAXXZ; SP_CONTROL::Remove(void)
0x140033783  cmp     byte ptr [rdi+1], 2
0x140033787  jnz     loc_1400336F7
0x14003378d  mov     rcx, rbp; this
0x140033790  call    ??1SP_CONTROL@@QEAA@XZ; SP_CONTROL::~SP_CONTROL(void)
0x140033795  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x1400337a0  call    ?UnInitializeLimiterInternal@SP_QOS_CONTEXT@@SAXXZ; SP_QOS_CONTEXT::UnInitializeLimiterInternal(void)
0x1400337a5  mov     rcx, rsi; DeviceObject
0x1400337a8  call    cs:__imp_IoDeleteDevice
0x1400337af  nop     dword ptr [rax+rax+00h]
0x1400337b4  jmp     loc_1400336F7
0x1400337b9  mov     edi, 0C0000010h
0x1400337be  jmp     short loc_1400337F1
0x1400337c0  call    cs:__imp_IoForwardIrpSynchronously
0x1400337c7  nop     dword ptr [rax+rax+00h]
0x1400337cc  xor     edi, edi
0x1400337ce  mov     qword ptr [rbx+38h], 20h ; ' '
0x1400337d6  jmp     short loc_1400337F1
0x1400337d8  call    ?SpQueryRootId@@YAJPEAVSP_CONTROL@@PEAU_IRP@@@Z; SpQueryRootId(SP_CONTROL *,_IRP *)
0x1400337dd  mov     edi, eax
0x1400337df  test    eax, eax
0x1400337e1  jns     short loc_14003380E
0x1400337e3  cmp     eax, r14d
0x1400337e6  jz      loc_1400336FE
0x1400337ec  cmp     edi, r14d
0x1400337ef  jz      short loc_1400337F6
0x1400337f1  mov     [rbx+30h], edi
0x1400337f4  jmp     short loc_1400337F9
0x1400337f6  mov     edi, [rbx+30h]
0x1400337f9  xor     edx, edx; PriorityBoost
0x1400337fb  mov     rcx, rbx; Irp
0x1400337fe  call    cs:__imp_IofCompleteRequest
0x140033805  nop     dword ptr [rax+rax+00h]
0x14003380a  mov     eax, edi
0x14003380c  jmp     short loc_140033825
0x14003380e  mov     [rbx+30h], eax
0x140033811  jmp     loc_1400336FE
0x140033816  mov     dword ptr [rdx+30h], 0
0x14003381d  mov     rcx, rsi; struct _DEVICE_OBJECT *
0x140033820  call    ?SpControlSkip@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; SpControlSkip(_DEVICE_OBJECT *,_IRP *)
0x140033825  add     rsp, 20h
0x140033829  pop     r15
0x14003382b  pop     r14
0x14003382d  pop     r12
0x14003382f  pop     rdi
0x140033830  pop     rsi
0x140033831  pop     rbp
0x140033832  pop     rbx
0x140033833  retn
```
