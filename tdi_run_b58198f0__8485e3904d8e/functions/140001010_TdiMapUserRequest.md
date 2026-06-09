# TdiMapUserRequest

- ea: `0x140001010`
- end: `0x140001338`
- name: `TdiMapUserRequest`
- size: `808`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, PIO_STACK_LOCATION IrpSp)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001010`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1400010a5`
- `ntoskrnl!IoIs32bitProcess` at `0x140001160`
- `ntoskrnl!IoIs32bitProcess` at `0x1400012b9`
- `ntoskrnl!IoIs32bitProcess` at `0x1400010a5`
- `ntoskrnl!IoIs32bitProcess` at `0x140001160`
- `ntoskrnl!IoIs32bitProcess` at `0x1400012b9`

## pseudocode

```c
NTSTATUS __stdcall TdiMapUserRequest(PDEVICE_OBJECT DeviceObject, PIRP Irp, PIO_STACK_LOCATION IrpSp)
{
  DWORD LowPart; // eax
  NTSTATUS v6; // ebx
  struct _LIST_ENTRY *Flink; // r8
  __int64 v9; // rdx
  struct _LIST_ENTRY *v10; // rax
  struct _IRP *MasterIrp; // rax
  ULONG Options; // ecx
  struct _IRP *v13; // r8
  __int64 Status; // rdx
  IO_STATUS_BLOCK *p_IoStatus; // r8
  __int64 v16; // r9
  unsigned int v17; // eax
  char *v18; // rdx
  struct _IRP *v19; // rax
  struct _IRP *v20; // rcx
  struct _IRP *v21; // rax
  struct _IRP *v22; // rax

  LowPart = IrpSp->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart != 2162724 )
  {
    v6 = -1073741811;
    switch ( LowPart )
    {
      case 0x210000u:
        if ( Irp->RequestorMode == 1 )
          return -1073741822;
        *(_WORD *)&IrpSp->MajorFunction = 1295;
        return 0;
      case 0x210004u:
        if ( Irp->RequestorMode == 1 )
          return -1073741822;
        if ( IrpSp->Parameters.Create.Options == 56 )
        {
          *(_WORD *)&IrpSp->MajorFunction = 783;
          Flink = Irp->AssociatedIrp.MasterIrp->ThreadListEntry.Flink;
          v9 = (__int64)&Flink[3] + SLODWORD(Flink->Flink);
          v10 = (struct _LIST_ENTRY *)(v9 + SLODWORD(Flink[1].Flink));
          Flink->Blink = Flink + 3;
          Flink[2].Blink = v10;
          v6 = 0;
          Flink[1].Blink = (struct _LIST_ENTRY *)v9;
          IrpSp->Parameters.QueryDirectory.FileName = (PUNICODE_STRING)Flink;
          IrpSp->Parameters.Read.ByteOffset.QuadPart = 0;
        }
        return v6;
      case 0x210008u:
        if ( Irp->RequestorMode == 1 )
          return -1073741822;
        *(_WORD *)&IrpSp->MajorFunction = 1551;
        return 0;
      case 0x21000Cu:
        if ( Irp->RequestorMode == 1 )
          return -1073741822;
        if ( IrpSp->Parameters.Create.Options == 56 )
        {
          MasterIrp = Irp->AssociatedIrp.MasterIrp;
          v6 = 0;
          *(_WORD *)&IrpSp->MajorFunction = 1039;
          IrpSp->Parameters.WMI.ProviderId = LOWORD(MasterIrp->IoStatus.Status);
        }
        return v6;
      case 0x210012u:
        if ( IoIs32bitProcess(Irp) )
          return -1073741822;
        Options = IrpSp->Parameters.Create.Options;
        if ( Options < 0x30 )
          return v6;
        v13 = Irp->AssociatedIrp.MasterIrp;
        *(_WORD *)&IrpSp->MajorFunction = 3087;
        IrpSp->Parameters.Read.Length = (ULONG)v13->ThreadListEntry.Flink;
        if ( Options - 48 < 0x30 )
        {
          p_IoStatus = 0;
        }
        else
        {
          Status = v13->IoStatus.Status;
          p_IoStatus = &v13->IoStatus;
          if ( Options - 96 < (unsigned int)Status )
            return v6;
          v16 = p_IoStatus[1].Status;
          v17 = Options - 96 - Status;
          if ( v17 < (unsigned int)v16 || v17 - (unsigned int)v16 < p_IoStatus[2].Status )
            return v6;
          v18 = (char *)&p_IoStatus[3] + Status;
          p_IoStatus->Information = (ULONG_PTR)&p_IoStatus[3];
          p_IoStatus[1].Information = (ULONG_PTR)v18;
          p_IoStatus[2].Information = (ULONG_PTR)&v18[v16];
        }
        IrpSp->Parameters.QueryDirectory.FileName = (PUNICODE_STRING)p_IoStatus;
        return 0;
      case 0x210016u:
        if ( Irp->RequestorMode == 1 )
          return -1073741822;
        if ( IrpSp->Parameters.Create.Options == 40 )
        {
          v19 = Irp->AssociatedIrp.MasterIrp;
          v6 = 0;
          *(_WORD *)&IrpSp->MajorFunction = 2063;
          *(&IrpSp->Parameters.Read.Length + 1) = LOWORD(v19->ThreadListEntry.Flink);
        }
        return v6;
      case 0x21001Au:
        if ( Irp->RequestorMode == 1 )
          return -1073741822;
        if ( IrpSp->Parameters.Create.Options == 56 )
        {
          v20 = Irp->AssociatedIrp.MasterIrp;
          v6 = 0;
          *(_WORD *)&IrpSp->MajorFunction = 2575;
          IrpSp->Parameters.Create.EaLength = LOWORD(v20->IoStatus.Status);
          *(LIST_ENTRY *)&IrpSp->Parameters.NotifyDirectoryEx.CompletionFilter = v20->ThreadListEntry;
        }
        return v6;
      case 0x21001Du:
        if ( Irp->RequestorMode == 1 )
          return -1073741822;
        if ( IrpSp->Parameters.Create.Options == 40 )
        {
          v21 = Irp->AssociatedIrp.MasterIrp;
          v6 = 0;
          *(_WORD *)&IrpSp->MajorFunction = 1807;
          *(&IrpSp->Parameters.Read.Length + 1) = LOWORD(v21->ThreadListEntry.Flink);
        }
        return v6;
      case 0x210021u:
        if ( Irp->RequestorMode == 1 )
          return -1073741822;
        if ( IrpSp->Parameters.Create.Options == 40 )
        {
          *(_WORD *)&IrpSp->MajorFunction = 2319;
          v6 = 0;
          IrpSp->Parameters.QueryDirectory.FileName = (PUNICODE_STRING)Irp->AssociatedIrp.MasterIrp->ThreadListEntry.Flink;
        }
        return v6;
      case 0x210029u:
        if ( IoIs32bitProcess(Irp) )
          return -1073741822;
        if ( IrpSp->Parameters.Create.Options == 48 )
        {
          v22 = Irp->AssociatedIrp.MasterIrp;
          v6 = 0;
          *(_WORD *)&IrpSp->MajorFunction = 3343;
          IrpSp->Parameters.Read.Length = (ULONG)v22->ThreadListEntry.Flink;
          IrpSp->Parameters.QueryDirectory.FileName = 0;
        }
        return v6;
      case 0x21002Cu:
        if ( Irp->RequestorMode == 1 )
          return -1073741822;
        if ( IrpSp->Parameters.Create.Options == 40 )
        {
          *(_WORD *)&IrpSp->MajorFunction = 271;
          v6 = 0;
          IrpSp->Parameters.WMI.ProviderId = (ULONG_PTR)Irp->AssociatedIrp.MasterIrp->ThreadListEntry.Flink;
        }
        return v6;
      case 0x210030u:
        if ( Irp->RequestorMode == 1 )
          return -1073741822;
        *(_WORD *)&IrpSp->MajorFunction = 527;
        return 0;
      case 0x210036u:
        if ( !IoIs32bitProcess(Irp) )
        {
          *(_WORD *)&IrpSp->MajorFunction = 3599;
          return 0;
        }
        return -1073741822;
      default:
        return -1073741822;
    }
  }
  return -1073741811;
}

```

## disassembly

```asm
0x140001010  mov     [rsp+arg_0], rbx
0x140001015  mov     [rsp+arg_8], rsi
0x14000101a  push    rdi
0x14000101b  sub     rsp, 20h
0x14000101f  mov     eax, [r8+18h]
0x140001023  mov     rdi, r8
0x140001026  mov     rsi, rdx
0x140001029  cmp     eax, 210024h
0x14000102e  jnz     short loc_140001048
0x140001030  mov     ebx, 0C000000Dh
0x140001035  mov     eax, ebx
0x140001037  mov     rbx, [rsp+28h+arg_0]
0x14000103c  mov     rsi, [rsp+28h+arg_8]
0x140001041  add     rsp, 20h
0x140001045  pop     rdi
0x140001046  retn
0x140001048  add     eax, 0FFDF0000h; switch 55 cases
0x14000104d  cmp     eax, 36h
0x140001050  jbe     short loc_14000106A
0x140001052  mov     rsi, [rsp+28h+arg_8]; jumptable 0000000140001088 default case, cases 2162689-2162691,2162693-2162695,2162697-2162699,2162701-2162705,2162707-2162709,2162711-2162713,2162715,2162716,2162718-2162720,2162722-2162728,2162730,2162731,2162733-2162735,2162737-2162741
0x140001057  mov     ebx, 0C0000002h
0x14000105c  mov     eax, ebx
0x14000105e  mov     rbx, [rsp+28h+arg_0]
0x140001063  add     rsp, 20h
0x140001067  pop     rdi
0x140001068  retn
0x14000106a  lea     rdx, cs:140000000h
0x140001071  mov     ebx, 0C000000Dh
0x140001076  movzx   eax, ds:(byte_140007308 - 140000000h)[rdx+rax]
0x14000107e  mov     ecx, ds:(jpt_140001088 - 140000000h)[rdx+rax*4]
0x140001085  add     rcx, rdx
0x140001088  jmp     rcx; switch jump
0x14000108e  cmp     byte ptr [rsi+40h], 1; jumptable 0000000140001088 case 2162688
0x140001092  jz      loc_14000132E
0x140001098  mov     word ptr [r8], 50Fh
0x14000109e  xor     ebx, ebx
0x1400010a0  jmp     short loc_140001035
0x1400010a2  mov     rcx, rsi; jumptable 0000000140001088 case 2162742
0x1400010a5  call    cs:__imp_IoIs32bitProcess
0x1400010ac  nop     dword ptr [rax+rax+00h]
0x1400010b1  test    al, al
0x1400010b3  jnz     loc_14000132E
0x1400010b9  mov     word ptr [rdi], 0E0Fh
0x1400010be  xor     ebx, ebx
0x1400010c0  jmp     loc_140001035
0x1400010c5  cmp     byte ptr [rsi+40h], 1; jumptable 0000000140001088 case 2162692
0x1400010c9  jz      loc_14000132E
0x1400010cf  cmp     dword ptr [r8+10h], 38h ; '8'
0x1400010d4  jnz     loc_140001035
0x1400010da  mov     word ptr [r8], 30Fh
0x1400010e0  mov     rax, [rsi+18h]
0x1400010e4  mov     r8, [rax+20h]
0x1400010e8  movsxd  rdx, dword ptr [r8]
0x1400010eb  lea     rcx, [r8+30h]
0x1400010ef  movsxd  rax, dword ptr [r8+10h]
0x1400010f3  add     rdx, rcx
0x1400010f6  add     rax, rdx
0x1400010f9  mov     [r8+8], rcx
0x1400010fd  mov     [r8+28h], rax
0x140001101  xor     ebx, ebx
0x140001103  mov     [r8+18h], rdx
0x140001107  mov     [rdi+10h], r8
0x14000110b  mov     qword ptr [rdi+18h], 0
0x140001113  jmp     loc_140001035
0x140001118  cmp     byte ptr [rsi+40h], 1; jumptable 0000000140001088 case 2162696
0x14000111c  jz      loc_14000132E
0x140001122  mov     word ptr [r8], 60Fh
0x140001128  xor     ebx, ebx
0x14000112a  jmp     loc_140001035
0x14000112f  cmp     byte ptr [rsi+40h], 1; jumptable 0000000140001088 case 2162700
0x140001133  jz      loc_14000132E
0x140001139  cmp     dword ptr [r8+10h], 38h ; '8'
0x14000113e  jnz     loc_140001035
0x140001144  mov     rax, [rsi+18h]
0x140001148  xor     ebx, ebx
0x14000114a  mov     word ptr [r8], 40Fh
0x140001150  movzx   eax, word ptr [rax+30h]
0x140001154  mov     [r8+8], rax
0x140001158  jmp     loc_140001035
0x14000115d  mov     rcx, rsi; jumptable 0000000140001088 case 2162706
0x140001160  call    cs:__imp_IoIs32bitProcess
0x140001167  nop     dword ptr [rax+rax+00h]
0x14000116c  test    al, al
0x14000116e  jnz     loc_14000132E
0x140001174  mov     ecx, [rdi+10h]
0x140001177  cmp     ecx, 30h ; '0'
0x14000117a  jb      loc_140001035
0x140001180  mov     r8, [rsi+18h]
0x140001184  mov     word ptr [rdi], 0C0Fh
0x140001189  mov     eax, [r8+20h]
0x14000118d  mov     [rdi+8], eax
0x140001190  lea     eax, [rcx-30h]
0x140001193  cmp     eax, 30h ; '0'
0x140001196  jb      short loc_1400011E0
0x140001198  movsxd  rdx, dword ptr [r8+30h]
0x14000119c  add     r8, 30h ; '0'
0x1400011a0  add     eax, 0FFFFFFD0h
0x1400011a3  cmp     eax, edx
0x1400011a5  jb      loc_140001035
0x1400011ab  movsxd  r9, dword ptr [r8+10h]
0x1400011af  sub     eax, edx
0x1400011b1  cmp     eax, r9d
0x1400011b4  jb      loc_140001035
0x1400011ba  sub     eax, r9d
0x1400011bd  cmp     eax, [r8+20h]
0x1400011c1  jb      loc_140001035
0x1400011c7  lea     rcx, [r8+30h]
0x1400011cb  add     rdx, rcx
0x1400011ce  mov     [r8+8], rcx
0x1400011d2  mov     [r8+18h], rdx
0x1400011d6  lea     rax, [rdx+r9]
0x1400011da  mov     [r8+28h], rax
0x1400011de  jmp     short loc_1400011E3
0x1400011e0  xor     r8d, r8d
0x1400011e3  mov     [rdi+10h], r8
0x1400011e7  xor     ebx, ebx
0x1400011e9  jmp     loc_140001035
0x1400011ee  cmp     byte ptr [rsi+40h], 1; jumptable 0000000140001088 case 2162710
0x1400011f2  jz      loc_14000132E
0x1400011f8  cmp     dword ptr [r8+10h], 28h ; '('
0x1400011fd  jnz     loc_140001035
0x140001203  mov     rax, [rsi+18h]
0x140001207  xor     ebx, ebx
0x140001209  mov     word ptr [r8], 80Fh
0x14000120f  movzx   eax, word ptr [rax+20h]
0x140001213  mov     [r8+0Ch], eax
0x140001217  jmp     loc_140001035
0x14000121c  cmp     byte ptr [rsi+40h], 1; jumptable 0000000140001088 case 2162714
0x140001220  jz      loc_14000132E
0x140001226  cmp     dword ptr [r8+10h], 38h ; '8'
0x14000122b  jnz     loc_140001035
0x140001231  mov     rcx, [rsi+18h]
0x140001235  xor     ebx, ebx
0x140001237  mov     word ptr [r8], 0A0Fh
0x14000123d  movzx   eax, word ptr [rcx+30h]
0x140001241  mov     [r8+20h], eax
0x140001245  mov     rax, [rcx+20h]
0x140001249  mov     [r8+10h], rax
0x14000124d  mov     rax, [rcx+28h]
0x140001251  mov     [r8+18h], rax
0x140001255  jmp     loc_140001035
0x14000125a  cmp     byte ptr [rsi+40h], 1; jumptable 0000000140001088 case 2162717
0x14000125e  jz      loc_14000132E
0x140001264  cmp     dword ptr [r8+10h], 28h ; '('
0x140001269  jnz     loc_140001035
0x14000126f  mov     rax, [rsi+18h]
0x140001273  xor     ebx, ebx
0x140001275  mov     word ptr [r8], 70Fh
0x14000127b  movzx   eax, word ptr [rax+20h]
0x14000127f  mov     [r8+0Ch], eax
0x140001283  jmp     loc_140001035
0x140001288  cmp     byte ptr [rsi+40h], 1; jumptable 0000000140001088 case 2162721
0x14000128c  jz      loc_14000132E
0x140001292  cmp     dword ptr [r8+10h], 28h ; '('
0x140001297  jnz     loc_140001035
0x14000129d  mov     word ptr [r8], 90Fh
0x1400012a3  xor     ebx, ebx
0x1400012a5  mov     rax, [rsi+18h]
0x1400012a9  mov     rcx, [rax+20h]
0x1400012ad  mov     [r8+10h], rcx
0x1400012b1  jmp     loc_140001035
0x1400012b6  mov     rcx, rsi; jumptable 0000000140001088 case 2162729
0x1400012b9  call    cs:__imp_IoIs32bitProcess
0x1400012c0  nop     dword ptr [rax+rax+00h]
0x1400012c5  test    al, al
0x1400012c7  jnz     short loc_14000132E
0x1400012c9  cmp     dword ptr [rdi+10h], 30h ; '0'
0x1400012cd  jnz     loc_140001035
0x1400012d3  mov     rax, [rsi+18h]
0x1400012d7  xor     ebx, ebx
0x1400012d9  mov     word ptr [rdi], 0D0Fh
0x1400012de  mov     eax, [rax+20h]
0x1400012e1  mov     [rdi+8], eax
0x1400012e4  mov     qword ptr [rdi+10h], 0
0x1400012ec  jmp     loc_140001035
0x1400012f1  cmp     byte ptr [rsi+40h], 1; jumptable 0000000140001088 case 2162732
0x1400012f5  jz      short loc_14000132E
0x1400012f7  cmp     dword ptr [r8+10h], 28h ; '('
0x1400012fc  jnz     loc_140001035
0x140001302  mov     word ptr [r8], 10Fh
0x140001308  xor     ebx, ebx
0x14000130a  mov     rax, [rsi+18h]
0x14000130e  mov     rcx, [rax+20h]
0x140001312  mov     [r8+8], rcx
0x140001316  jmp     loc_140001035
0x14000131b  cmp     byte ptr [rsi+40h], 1; jumptable 0000000140001088 case 2162736
0x14000131f  jz      short loc_14000132E
0x140001321  mov     word ptr [r8], 20Fh
0x140001327  xor     ebx, ebx
0x140001329  jmp     loc_140001035
0x14000132e  mov     eax, 0C0000002h
0x140001333  jmp     loc_140001037
```
