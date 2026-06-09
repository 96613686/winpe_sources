# VmpQueryDeviceName(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x1400156d0`
- end: `0x1400157f9`
- name: `?VmpQueryDeviceName@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `297`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140005050`
- `0x140005240`
- `0x1400156d0`

## import_xrefs

- `ntoskrnl!_itow_s` at `0x140015753`
- `ntoskrnl!_itow_s` at `0x140015753`

## pseudocode

```c
__int64 __fastcall VmpQueryDeviceName(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  int v4; // ecx
  __int16 v5; // bp
  struct _IRP *MasterIrp; // rdx
  __int64 v7; // rax
  __int64 v9; // rax
  __int128 Src; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v11[28]; // [rsp+40h] [rbp-68h]
  wchar_t v12[18]; // [rsp+5Ch] [rbp-4Ch] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Read.Length < 4 )
    return 3221225485LL;
  v4 = *((_DWORD *)a1 + 41);
  Src = *(_OWORD *)L"\\Device\\HarddiskVolume";
  v5 = 22;
  *(_OWORD *)v11 = *(_OWORD *)L"HarddiskVolume";
  *(_OWORD *)&v11[12] = *(_OWORD *)L"skVolume";
  if ( _itow_s(v4, v12, 0xBu, 10) >= 0 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v12[v9] );
    v5 = 22 - 2 * v9;
  }
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  v7 = (unsigned __int16)(66 - v5);
  MasterIrp->Type = v7;
  a2->IoStatus.Information = v7 + 2;
  if ( CurrentStackLocation->Parameters.Read.Length < (unsigned __int64)(v7 + 2) )
  {
    a2->IoStatus.Information = 2;
    return 2147483653LL;
  }
  else
  {
    memmove(&MasterIrp->Size, &Src, (unsigned __int16)MasterIrp->Type);
    return 0;
  }
}

```

## disassembly

```asm
0x1400156d0  mov     r11, rsp
0x1400156d3  push    rsi
0x1400156d4  push    rdi
0x1400156d5  sub     rsp, 98h
0x1400156dc  mov     rax, cs:__security_cookie
0x1400156e3  xor     rax, rsp
0x1400156e6  mov     [rsp+0A8h+var_28], rax
0x1400156ee  mov     rsi, [rdx+0B8h]
0x1400156f5  mov     rdi, rdx
0x1400156f8  mov     eax, 42h ; 'B'
0x1400156fd  cmp     dword ptr [rsi+8], 4
0x140015701  jb      loc_1400157C2
0x140015707  movups  xmm0, xmmword ptr cs:aDeviceHarddisk_0; "\\Device\\HarddiskVolume"
0x14001570e  mov     ecx, [rcx+0A4h]; Val
0x140015714  mov     r9d, 0Ah; Radix
0x14001571a  movups  xmm1, xmmword ptr cs:aDeviceHarddisk_0+10h; "HarddiskVolume"
0x140015721  mov     [r11+18h], rbx
0x140015725  lea     rdx, [r11-4Ch]; DstBuf
0x140015729  movzx   ebx, ax
0x14001572c  mov     [r11-18h], rbp
0x140015730  sub     ax, 2Ch ; ','
0x140015734  movaps  [rsp+0A8h+Src], xmm0
0x140015739  movups  xmm0, xmmword ptr cs:aDeviceHarddisk_0+1Ch; "skVolume"
0x140015740  movzx   ebp, ax
0x140015743  movaps  xmmword ptr [rsp+0A8h+var_68], xmm1
0x140015748  mov     r8d, ebp
0x14001574b  shr     r8, 1; SizeInWords
0x14001574e  movups  xmmword ptr [rsp+0A8h+var_68+0Ch], xmm0
0x140015753  call    cs:__imp__itow_s
0x14001575a  nop     dword ptr [rax+rax+00h]
0x14001575f  test    eax, eax
0x140015761  jns     short loc_1400157C9
0x140015763  movzx   eax, bp
0x140015766  mov     rbp, [rsp+0A8h+var_18]
0x14001576e  mov     rdx, [rdi+18h]
0x140015772  sub     bx, ax
0x140015775  movzx   eax, bx
0x140015778  mov     rbx, [rsp+0A8h+arg_10]
0x140015780  mov     [rdx], ax
0x140015783  lea     rcx, [rax+2]
0x140015787  mov     [rdi+38h], rcx
0x14001578b  mov     eax, [rsi+8]
0x14001578e  cmp     rax, rcx
0x140015791  jb      short loc_1400157EA
0x140015793  movzx   r8d, word ptr [rdx]; Size
0x140015797  lea     rcx, [rdx+2]; void *
0x14001579b  lea     rdx, [rsp+0A8h+Src]; Src
0x1400157a0  call    memmove
0x1400157a5  xor     eax, eax
0x1400157a7  mov     rcx, [rsp+0A8h+var_28]
0x1400157af  xor     rcx, rsp; StackCookie
0x1400157b2  call    __security_check_cookie
0x1400157b7  add     rsp, 98h
0x1400157be  pop     rdi
0x1400157bf  pop     rsi
0x1400157c0  retn
0x1400157c2  mov     eax, 0C000000Dh
0x1400157c7  jmp     short loc_1400157A7
0x1400157c9  lea     rcx, [rsp+0A8h+var_4C]
0x1400157ce  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400157d5  inc     rax
0x1400157d8  cmp     word ptr [rcx+rax*2], 0
0x1400157dd  jnz     short loc_1400157D5
0x1400157df  add     ax, ax
0x1400157e2  sub     bp, ax
0x1400157e5  jmp     loc_140015763
0x1400157ea  mov     qword ptr [rdi+38h], 2
0x1400157f2  mov     eax, 80000005h
0x1400157f7  jmp     short loc_1400157A7
```
