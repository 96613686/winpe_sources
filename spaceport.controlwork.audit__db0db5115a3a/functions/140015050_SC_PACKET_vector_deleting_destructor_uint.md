# SC_PACKET::`vector deleting destructor'(uint)

- ea: `0x140015050`
- end: `0x140015196`
- name: `??_ESC_PACKET@@UEAAPEAXI@Z`
- size: `326`
- prototype: `void *__fastcall(PVOID Buffer, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x140015050`
- `0x1400151a0`
- `0x140068000`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1400150dc`
- `ntoskrnl!IoFreeMdl` at `0x1400150dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001517e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001517e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400150c8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400150c8`
- `ntoskrnl!MmFreePagesFromMdl` at `0x140015168`
- `ntoskrnl!MmFreePagesFromMdl` at `0x140015168`

## pseudocode

```c
char *__fastcall SC_PACKET::`vector deleting destructor'(char *Buffer, char a2)
{
  _QWORD **v3; // rdi
  _QWORD *v5; // rax
  int v6; // eax
  struct _MDL *v7; // rdi
  _QWORD *v9; // rcx

  *(_QWORD *)Buffer = &SC_PACKET::`vftable';
  v3 = (_QWORD **)(Buffer + 96);
  while ( 1 )
  {
    v5 = *v3;
    if ( *v3 == v3 )
      break;
    if ( (_QWORD **)v5[1] != v3 || (v9 = (_QWORD *)*v5, *(_QWORD **)(*v5 + 8LL) != v5) )
      __fastfail(3u);
    *v3 = v9;
    v9[1] = v3;
    if ( v5 != (_QWORD *)200 )
      (*(void (__fastcall **)(_QWORD *, __int64))*(v5 - 25))(v5 - 25, 1);
  }
  *((_DWORD *)Buffer + 19) &= ~1u;
  v6 = *((_DWORD *)Buffer + 28);
  v7 = (struct _MDL *)*((_QWORD *)Buffer + 15);
  if ( v6 == 3 )
  {
    if ( *((_WORD *)Buffer + 58) == 0xFFFF )
      ExFreePoolWithTag((char *)v7->StartVa + v7->ByteOffset, 0);
    else
      ExFreeToNPagedLookasideList(
        (PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 45)
                               + ((unsigned __int64)*((unsigned __int16 *)Buffer + 58) << 7)),
        (char *)v7->StartVa + v7->ByteOffset);
  }
  else if ( v6 != 2 )
  {
    if ( v6 != 4 )
      goto LABEL_8;
    MmFreePagesFromMdl(v7);
  }
  if ( v7 )
    IoFreeMdl(v7);
LABEL_8:
  *((_WORD *)Buffer + 58) = -1;
  *((_DWORD *)Buffer + 28) = 0;
  *((_QWORD *)Buffer + 15) = 0;
  if ( (a2 & 1) != 0 )
    SC_PACKET::operator delete(Buffer);
  return Buffer;
}

```

## disassembly

```asm
0x140015050  mov     [rsp+arg_8], rbx
0x140015055  mov     [rsp+arg_10], rsi
0x14001505a  push    rdi
0x14001505b  sub     rsp, 20h
0x14001505f  lea     rax, ??_7SC_PACKET@@6B@; const SC_PACKET::`vftable'
0x140015066  mov     esi, edx
0x140015068  mov     [rcx], rax
0x14001506b  lea     rdi, [rcx+60h]
0x14001506f  mov     rbx, rcx
0x140015072  mov     rax, [rdi]
0x140015075  cmp     rax, rdi
0x140015078  jnz     loc_14001511C
0x14001507e  and     dword ptr [rbx+4Ch], 0FFFFFFFEh
0x140015082  mov     eax, [rbx+70h]
0x140015085  mov     rdi, [rbx+78h]
0x140015089  mov     [rsp+28h+arg_0], rbp
0x14001508e  mov     ebp, 0FFFFh
0x140015093  cmp     eax, 3
0x140015096  jnz     loc_140015157
0x14001509c  mov     r8d, [rdi+2Ch]
0x1400150a0  add     r8, [rdi+20h]
0x1400150a4  movzx   edx, word ptr [rbx+74h]
0x1400150a8  cmp     dx, bp
0x1400150ab  jz      loc_140015179
0x1400150b1  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400150b8  mov     ecx, edx
0x1400150ba  shl     rcx, 7
0x1400150be  mov     rdx, r8; Entry
0x1400150c1  add     rcx, [rax+168h]; Lookaside
0x1400150c8  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400150cf  nop     dword ptr [rax+rax+00h]
0x1400150d4  test    rdi, rdi
0x1400150d7  jz      short loc_1400150E8
0x1400150d9  mov     rcx, rdi; Mdl
0x1400150dc  call    cs:__imp_IoFreeMdl
0x1400150e3  nop     dword ptr [rax+rax+00h]
0x1400150e8  xor     eax, eax
0x1400150ea  mov     [rbx+74h], bp
0x1400150ee  mov     rbp, [rsp+28h+arg_0]
0x1400150f3  mov     [rbx+70h], eax
0x1400150f6  mov     [rbx+78h], rax
0x1400150fa  test    sil, 1
0x1400150fe  jz      short loc_140015108
0x140015100  mov     rcx, rbx; Buffer
0x140015103  call    ??3SC_PACKET@@SAXPEAX@Z; SC_PACKET::operator delete(void *)
0x140015108  mov     rsi, [rsp+28h+arg_10]
0x14001510d  mov     rax, rbx
0x140015110  mov     rbx, [rsp+28h+arg_8]
0x140015115  add     rsp, 20h
0x140015119  pop     rdi
0x14001511a  retn
0x14001511c  cmp     [rax+8], rdi
0x140015120  jnz     short loc_14001518F
0x140015122  mov     rcx, [rax]
0x140015125  cmp     [rcx+8], rax
0x140015129  jnz     short loc_14001518F
0x14001512b  mov     [rdi], rcx
0x14001512e  mov     [rcx+8], rdi
0x140015132  lea     rcx, [rax-0C8h]
0x140015139  test    rcx, rcx
0x14001513c  jz      loc_140015072
0x140015142  mov     rax, [rcx]
0x140015145  mov     edx, 1
0x14001514a  mov     rax, [rax]
0x14001514d  call    _guard_dispatch_icall
0x140015152  jmp     loc_140015072
0x140015157  cmp     eax, 2
0x14001515a  jz      loc_1400150D4
0x140015160  cmp     eax, 4
0x140015163  jnz     short loc_1400150E8
0x140015165  mov     rcx, rdi; MemoryDescriptorList
0x140015168  call    cs:__imp_MmFreePagesFromMdl
0x14001516f  nop     dword ptr [rax+rax+00h]
0x140015174  jmp     loc_1400150D4
0x140015179  xor     edx, edx; Tag
0x14001517b  mov     rcx, r8; P
0x14001517e  call    cs:__imp_ExFreePoolWithTag
0x140015185  nop     dword ptr [rax+rax+00h]
0x14001518a  jmp     loc_1400150D4
0x14001518f  mov     ecx, 3
0x140015194  int     29h; Win8: RtlFailFast(ecx)
```
