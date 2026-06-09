# SIO_LOG_PACKET::~SIO_LOG_PACKET(void)

- ea: `0x14000a070`
- end: `0x14000a195`
- name: `??1SIO_LOG_PACKET@@UEAA@XZ`
- size: `293`
- prototype: `void __fastcall(SIO_LOG_PACKET *__hidden this)`
- caller_count: `41`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140008260`
- `0x140011ca0`
- `0x140014bc0`
- `0x140014fd0`
- `0x140018210`
- `0x14001dd60`
- `0x14001dfb0`
- `0x14001faa0`
- `0x14002f8c0`
- `0x14002f938`
- `0x14003e8e8`
- `0x14003e940`
- `0x14003f398`
- `0x14003f8f4`
- `0x14003fb30`
- `0x14003fbf8`
- `0x1400401a0`
- `0x140041b4c`
- `0x140041c7c`
- `0x1400479b0`
- `0x140047c64`
- `0x140047d4c`
- `0x140048918`
- `0x140048b20`
- `0x140049740`
- `0x140049cb0`
- `0x14004f580`
- `0x140050fb4`
- `0x14005116c`
- `0x140052850`
- `0x140052ff0`
- `0x140059ef4`
- `0x14005b414`
- `0x1400b0c40`
- `0x1400b1190`
- `0x1400b1460`
- `0x1400b18b4`
- `0x1400b1b48`
- `0x1400b1c98`
- `0x1400b2348`
- `0x1400b25c0`

## callees

- `0x14000a070`
- `0x140068150`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14000a0f5`
- `ntoskrnl!IoFreeMdl` at `0x14000a0f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a17d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a17d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000a0e1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000a0e1`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14000a167`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14000a167`

## pseudocode

```c
void __fastcall SIO_LOG_PACKET::~SIO_LOG_PACKET(SIO_LOG_PACKET *this)
{
  _QWORD **v2; // rdi
  _QWORD *v3; // rax
  int v4; // eax
  struct _MDL *v5; // rdi
  _QWORD *v6; // rcx

  *(_QWORD *)this = &SC_PACKET::`vftable';
  v2 = (_QWORD **)((char *)this + 96);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    if ( (_QWORD **)v3[1] != v2 || (v6 = (_QWORD *)*v3, *(_QWORD **)(*v3 + 8LL) != v3) )
      __fastfail(3u);
    *v2 = v6;
    v6[1] = v2;
    if ( v3 != (_QWORD *)200 )
      (*(void (__fastcall **)(_QWORD *, __int64))*(v3 - 25))(v3 - 25, 1);
  }
  *((_DWORD *)this + 19) &= ~1u;
  v4 = *((_DWORD *)this + 28);
  v5 = (struct _MDL *)*((_QWORD *)this + 15);
  if ( v4 == 3 )
  {
    if ( *((_WORD *)this + 58) == 0xFFFF )
      ExFreePoolWithTag((char *)v5->StartVa + v5->ByteOffset, 0);
    else
      ExFreeToNPagedLookasideList(
        (PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 45)
                               + ((unsigned __int64)*((unsigned __int16 *)this + 58) << 7)),
        (char *)v5->StartVa + v5->ByteOffset);
  }
  else if ( v4 != 2 )
  {
    if ( v4 != 4 )
      goto LABEL_8;
    MmFreePagesFromMdl(v5);
  }
  if ( v5 )
    IoFreeMdl(v5);
LABEL_8:
  *((_WORD *)this + 58) = -1;
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 15) = 0;
}

```

## disassembly

```asm
0x14000a070  mov     [rsp+arg_8], rbx
0x14000a075  push    rdi
0x14000a076  sub     rsp, 20h
0x14000a07a  lea     rax, ??_7SC_PACKET@@6B@; const SC_PACKET::`vftable'
0x14000a081  mov     rbx, rcx
0x14000a084  mov     [rcx], rax
0x14000a087  lea     rdi, [rcx+60h]
0x14000a08b  mov     rax, [rdi]
0x14000a08e  cmp     rax, rdi
0x14000a091  jnz     loc_14000A11F
0x14000a097  and     dword ptr [rbx+4Ch], 0FFFFFFFEh
0x14000a09b  mov     eax, [rbx+70h]
0x14000a09e  mov     rdi, [rbx+78h]
0x14000a0a2  mov     [rsp+28h+arg_0], rsi
0x14000a0a7  mov     esi, 0FFFFh
0x14000a0ac  cmp     eax, 3
0x14000a0af  jnz     loc_14000A15A
0x14000a0b5  mov     r8d, [rdi+2Ch]
0x14000a0b9  add     r8, [rdi+20h]
0x14000a0bd  movzx   edx, word ptr [rbx+74h]
0x14000a0c1  cmp     dx, si
0x14000a0c4  jz      loc_14000A178
0x14000a0ca  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14000a0d1  mov     ecx, edx
0x14000a0d3  shl     rcx, 7
0x14000a0d7  mov     rdx, r8; Entry
0x14000a0da  add     rcx, [rax+168h]; Lookaside
0x14000a0e1  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000a0e8  nop     dword ptr [rax+rax+00h]
0x14000a0ed  test    rdi, rdi
0x14000a0f0  jz      short loc_14000A101
0x14000a0f2  mov     rcx, rdi; Mdl
0x14000a0f5  call    cs:__imp_IoFreeMdl
0x14000a0fc  nop     dword ptr [rax+rax+00h]
0x14000a101  xor     eax, eax
0x14000a103  mov     [rbx+74h], si
0x14000a107  mov     rsi, [rsp+28h+arg_0]
0x14000a10c  mov     [rbx+70h], eax
0x14000a10f  mov     [rbx+78h], rax
0x14000a113  mov     rbx, [rsp+28h+arg_8]
0x14000a118  add     rsp, 20h
0x14000a11c  pop     rdi
0x14000a11d  retn
0x14000a11f  cmp     [rax+8], rdi
0x14000a123  jnz     short loc_14000A18E
0x14000a125  mov     rcx, [rax]
0x14000a128  cmp     [rcx+8], rax
0x14000a12c  jnz     short loc_14000A18E
0x14000a12e  mov     [rdi], rcx
0x14000a131  mov     [rcx+8], rdi
0x14000a135  lea     rcx, [rax-0C8h]
0x14000a13c  test    rcx, rcx
0x14000a13f  jz      loc_14000A08B
0x14000a145  mov     rax, [rcx]
0x14000a148  mov     edx, 1
0x14000a14d  mov     rax, [rax]
0x14000a150  call    _guard_dispatch_icall
0x14000a155  jmp     loc_14000A08B
0x14000a15a  cmp     eax, 2
0x14000a15d  jz      short loc_14000A0ED
0x14000a15f  cmp     eax, 4
0x14000a162  jnz     short loc_14000A101
0x14000a164  mov     rcx, rdi; MemoryDescriptorList
0x14000a167  call    cs:__imp_MmFreePagesFromMdl
0x14000a16e  nop     dword ptr [rax+rax+00h]
0x14000a173  jmp     loc_14000A0ED
0x14000a178  xor     edx, edx; Tag
0x14000a17a  mov     rcx, r8; P
0x14000a17d  call    cs:__imp_ExFreePoolWithTag
0x14000a184  nop     dword ptr [rax+rax+00h]
0x14000a189  jmp     loc_14000A0ED
0x14000a18e  mov     ecx, 3
0x14000a193  int     29h; Win8: RtlFailFast(ecx)
```
