# VmpManageBypassIo(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140016760`
- end: `0x14001697b`
- name: `?VmpManageBypassIo@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `539`
- prototype: `int(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001ae0`

## callees

- `0x1400029e0`
- `0x140002a30`
- `0x140005050`
- `0x140005540`
- `0x140016760`
- `0x140016990`

## import_xrefs

- `ntoskrnl!wcscpy_s` at `0x140016904`
- `ntoskrnl!wcscpy_s` at `0x14001691e`
- `ntoskrnl!wcscpy_s` at `0x140016904`
- `ntoskrnl!wcscpy_s` at `0x14001691e`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14001682c`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14001682c`
- `ntoskrnl!IofCompleteRequest` at `0x140016953`
- `ntoskrnl!IofCompleteRequest` at `0x140016953`

## pseudocode

```c
__int64 __fastcall VmpManageBypassIo(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  struct VM_ROOT_EXTENSION *v3; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  int Status; // ebx
  struct _IRP *MasterIrp; // r14
  int MdlAddress; // r15d
  __int64 v9; // rax
  __int64 v10; // rcx
  wchar_t Src[12]; // [rsp+20h] [rbp-88h] BYREF
  _OWORD v13[4]; // [rsp+38h] [rbp-70h] BYREF

  v3 = (struct VM_ROOT_EXTENSION *)*((_QWORD *)a1 + 1);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  wcscpy(Src, L"volmgrsys");
  wcscpy((wchar_t *)v13, L"Dynamic volumes not pported");
  VmpAcquireAll(v3);
  if ( (unsigned __int8)VmpIsVolumeDead(a1) )
  {
    Status = -1073741810;
  }
  else if ( CurrentStackLocation->Parameters.Create.Options >= 0x18 )
  {
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    MdlAddress = (int)MasterIrp->MdlAddress;
    if ( *((_BYTE *)a1 + 426) )
    {
      Status = 0;
      if ( ((MdlAddress - 1) & 0xFFFFFFFD) == 0 )
      {
        if ( CurrentStackLocation->Parameters.Read.Length >= 0x160 )
        {
          memset(MasterIrp, 0, CurrentStackLocation->Parameters.Read.Length);
          v9 = -1;
          *(_DWORD *)&MasterIrp->Type = 352;
          v10 = -1;
          *(_DWORD *)(&MasterIrp->Size + 1) = 352;
          LODWORD(MasterIrp->MdlAddress) = MdlAddress;
          MasterIrp->AssociatedIrp.IrpCount = -1073740602;
          do
            ++v10;
          while ( Src[v10] );
          WORD2(MasterIrp->AssociatedIrp.SystemBuffer) = v10;
          do
            ++v9;
          while ( *((_WORD *)v13 + v9) );
          HIWORD(MasterIrp->Overlay.AllocationSize.QuadPart) = v9;
          wcscpy_s((wchar_t *)&MasterIrp->AssociatedIrp.SystemBuffer + 3, 0x40u, Src);
          wcscpy_s((wchar_t *)&MasterIrp->Overlay.AllocationSize + 4, 0x100u, (const wchar_t *)v13);
          a2->IoStatus.Information = 352;
        }
        else
        {
          Status = -1073741789;
        }
      }
    }
    else
    {
      IoForwardIrpSynchronously(*((PDEVICE_OBJECT *)a1 + 43), a2);
      Status = a2->IoStatus.Status;
      if ( Status >= 0 )
      {
        if ( MdlAddress == 2 )
        {
          *((_BYTE *)a1 + 144) = 0;
        }
        else if ( MdlAddress == 1 && a2->AssociatedIrp.MasterIrp->AssociatedIrp.IrpCount >= 0 )
        {
          *((_BYTE *)a1 + 144) = 1;
        }
      }
    }
  }
  else
  {
    Status = -1073741820;
  }
  VmpReleaseAll(*((struct VM_ROOT_EXTENSION **)a1 + 1));
  a2->IoStatus.Status = Status;
  IofCompleteRequest(a2, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140016760  push    rbx
0x140016762  push    rbp
0x140016763  push    rsi
0x140016764  push    rdi
0x140016765  sub     rsp, 88h
0x14001676c  mov     rax, cs:__security_cookie
0x140016773  xor     rax, rsp
0x140016776  mov     [rsp+0A8h+var_30], rax
0x14001677b  movups  xmm0, xmmword ptr cs:aVolmgrSys; "volmgr.sys"
0x140016782  mov     rsi, rcx
0x140016785  mov     rcx, [rcx+8]; struct VM_ROOT_EXTENSION *
0x140016789  movsd   xmm1, qword ptr cs:aVolmgrSys+0Eh; "sys"
0x140016791  mov     rdi, rdx
0x140016794  mov     rbp, [rdx+0B8h]
0x14001679b  movups  xmmword ptr [rsp+0A8h+Src], xmm0
0x1400167a0  movups  xmm0, xmmword ptr cs:aDynamicVolumes; "Dynamic volumes not supported"
0x1400167a7  movsd   qword ptr [rsp+0A8h+Src+0Eh], xmm1
0x1400167ad  movups  xmm1, xmmword ptr cs:aDynamicVolumes+10h; "volumes not supported"
0x1400167b4  movups  xmmword ptr [rsp+0A8h+var_70], xmm0
0x1400167b9  movups  xmm0, xmmword ptr cs:aDynamicVolumes+20h; "not supported"
0x1400167c0  movups  xmmword ptr [rsp+0A8h+var_70+10h], xmm1
0x1400167c5  movups  xmm1, xmmword ptr cs:aDynamicVolumes+2Ch; "pported"
0x1400167cc  movups  [rsp+0A8h+var_50], xmm0
0x1400167d1  movups  [rsp+0A8h+var_50+0Ch], xmm1
0x1400167d6  call    ?VmpAcquireAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireAll(VM_ROOT_EXTENSION *)
0x1400167db  mov     rcx, rsi
0x1400167de  call    VmpIsVolumeDead
0x1400167e3  test    al, al
0x1400167e5  jz      short loc_1400167F1
0x1400167e7  mov     ebx, 0C000000Eh
0x1400167ec  jmp     loc_140016942
0x1400167f1  cmp     dword ptr [rbp+10h], 18h
0x1400167f5  jnb     short loc_140016801
0x1400167f7  mov     ebx, 0C0000004h
0x1400167fc  jmp     loc_140016942
0x140016801  cmp     byte ptr [rsi+1AAh], 0
0x140016808  mov     [rsp+0A8h+arg_10], r14
0x140016810  mov     r14, [rdi+18h]
0x140016814  mov     [rsp+0A8h+var_28], r15
0x14001681c  mov     r15d, [r14+8]
0x140016820  jnz     short loc_140016879
0x140016822  mov     rcx, [rsi+158h]; DeviceObject
0x140016829  mov     rdx, rdi; Irp
0x14001682c  call    cs:__imp_IoForwardIrpSynchronously
0x140016833  nop     dword ptr [rax+rax+00h]
0x140016838  mov     ebx, [rdi+30h]
0x14001683b  test    ebx, ebx
0x14001683d  js      loc_140016932
0x140016843  cmp     r15d, 2
0x140016847  jnz     short loc_140016855
0x140016849  mov     byte ptr [rsi+90h], 0
0x140016850  jmp     loc_140016932
0x140016855  cmp     r15d, 1
0x140016859  jnz     loc_140016932
0x14001685f  mov     rax, [rdi+18h]
0x140016863  cmp     dword ptr [rax+18h], 0
0x140016867  jl      loc_140016932
0x14001686d  mov     [rsi+90h], r15b
0x140016874  jmp     loc_140016932
0x140016879  xor     ebx, ebx
0x14001687b  lea     eax, [r15-1]
0x14001687f  test    eax, 0FFFFFFFDh
0x140016884  jnz     loc_140016932
0x14001688a  mov     eax, [rbp+8]
0x14001688d  cmp     eax, 160h
0x140016892  jnb     short loc_14001689E
0x140016894  mov     ebx, 0C0000023h
0x140016899  jmp     loc_140016932
0x14001689e  mov     r8, rax; Size
0x1400168a1  xor     edx, edx; Val
0x1400168a3  mov     rcx, r14; void *
0x1400168a6  call    memset
0x1400168ab  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400168b2  mov     dword ptr [r14], 160h
0x1400168b9  mov     rcx, rax
0x1400168bc  mov     dword ptr [r14+4], 160h
0x1400168c4  mov     [r14+8], r15d
0x1400168c8  lea     rdx, [rsp+0A8h+Src]
0x1400168cd  mov     dword ptr [r14+18h], 0C00004C6h
0x1400168d5  inc     rcx
0x1400168d8  cmp     [rdx+rcx*2], bx
0x1400168dc  jnz     short loc_1400168D5
0x1400168de  mov     [r14+1Ch], cx
0x1400168e3  lea     rcx, [rsp+0A8h+var_70]
0x1400168e8  inc     rax
0x1400168eb  cmp     [rcx+rax*2], bx
0x1400168ef  jnz     short loc_1400168E8
0x1400168f1  lea     rcx, [r14+1Eh]; Dst
0x1400168f5  mov     [r14+5Eh], ax
0x1400168fa  lea     r8, [rsp+0A8h+Src]; Src
0x1400168ff  mov     edx, 40h ; '@'; SizeInWords
0x140016904  call    cs:__imp_wcscpy_s
0x14001690b  nop     dword ptr [rax+rax+00h]
0x140016910  lea     rcx, [r14+60h]; Dst
0x140016914  mov     edx, 100h; SizeInWords
0x140016919  lea     r8, [rsp+0A8h+var_70]; Src
0x14001691e  call    cs:__imp_wcscpy_s
0x140016925  nop     dword ptr [rax+rax+00h]
0x14001692a  mov     qword ptr [rdi+38h], 160h
0x140016932  mov     r14, [rsp+0A8h+arg_10]
0x14001693a  mov     r15, [rsp+0A8h+var_28]
0x140016942  mov     rcx, [rsi+8]; struct VM_ROOT_EXTENSION *
0x140016946  call    ?VmpReleaseAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseAll(VM_ROOT_EXTENSION *)
0x14001694b  xor     edx, edx; PriorityBoost
0x14001694d  mov     [rdi+30h], ebx
0x140016950  mov     rcx, rdi; Irp
0x140016953  call    cs:__imp_IofCompleteRequest
0x14001695a  nop     dword ptr [rax+rax+00h]
0x14001695f  mov     eax, ebx
0x140016961  mov     rcx, [rsp+0A8h+var_30]
0x140016966  xor     rcx, rsp; StackCookie
0x140016969  call    __security_check_cookie
0x14001696e  add     rsp, 88h
0x140016975  pop     rdi
0x140016976  pop     rsi
0x140016977  pop     rbp
0x140016978  pop     rbx
0x140016979  retn
```
