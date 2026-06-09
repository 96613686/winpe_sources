# Tpm20Context::CompleteTpm20Request(Tpm20Request *,long)

- ea: `0x14000e98c`
- end: `0x14000eacc`
- name: `?CompleteTpm20Request@Tpm20Context@@SAXPEAVTpm20Request@@J@Z`
- size: `320`
- prototype: `void __fastcall(struct Tpm20Request *this, int)`
- caller_count: `9`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140003380`
- `0x140003c30`
- `0x14000463c`
- `0x14000e3ac`
- `0x14000e8b0`
- `0x1400171d0`
- `0x14001aaa4`
- `0x14001c7cc`
- `0x14001c944`

## callees

- `0x1400088ec`
- `0x140008a40`
- `0x14000e98c`
- `0x14000ead4`
- `0x140039780`
- `0x140039840`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ea3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ea3c`
- `ntoskrnl!KeSetEvent` at `0x14000ea98`
- `ntoskrnl!KeSetEvent` at `0x14000ea98`

## pseudocode

```c
void __fastcall Tpm20Context::CompleteTpm20Request(const void **this, unsigned int a2)
{
  unsigned int v2; // edi
  unsigned __int32 v4; // edx
  void *v5; // rcx
  unsigned int v6; // ecx
  const void *v7; // rdx
  struct Tpm20Resource *v8; // rcx
  void *v9; // rcx
  void (*v10)(void); // rax

  v2 = a2;
  if ( a2 == -1073741536 )
  {
    Tpm20Request::FormatTpm20Error((Tpm20Request *)this, 0x909u);
    v2 = 0;
  }
  else if ( a2 )
  {
LABEL_13:
    v6 = 0;
    goto LABEL_7;
  }
  v4 = *((_DWORD *)this + 47);
  if ( _byteswap_ulong(*(_DWORD *)((char *)this[4] + 2)) > v4 )
  {
    v2 = -2147483643;
    goto LABEL_13;
  }
  v5 = (void *)this[31];
  if ( v5 )
    memmove(v5, this[4], v4);
  v6 = *((_DWORD *)this + 47);
LABEL_7:
  v7 = this[27];
  if ( v7 )
  {
    (*((void (__fastcall **)(PKDPC, const void *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 265))(
      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
      v7,
      v2,
      v6);
    this[27] = 0;
  }
  else
  {
    *((_DWORD *)this[28] + 8) = v2;
    *((_DWORD *)this[28] + 9) = v6;
    v9 = (void *)this[28];
    v10 = (void (*)(void))*((_QWORD *)v9 + 3);
    if ( v10 )
      v10();
    else
      KeSetEvent((PRKEVENT)v9, 0, 0);
    this[28] = 0;
  }
  v8 = (struct Tpm20Resource *)this[21];
  if ( v8 )
  {
    Tpm20Context::DeleteTpm20Resource(v8);
    this[21] = 0;
  }
  Tpm20Request::~Tpm20Request((Tpm20Request *)this);
  ExFreePoolWithTag(this - 2, 0x506D7054u);
}

```

## disassembly

```asm
0x14000e98c  mov     [rsp+arg_0], rbx
0x14000e991  push    rdi
0x14000e992  sub     rsp, 30h
0x14000e996  mov     edi, edx
0x14000e998  mov     rbx, rcx
0x14000e99b  cmp     edx, 0C0000120h
0x14000e9a1  jz      loc_14000EAA6
0x14000e9a7  test    edx, edx
0x14000e9a9  jnz     loc_14000EA59
0x14000e9af  mov     r9, [rbx+20h]
0x14000e9b3  mov     edx, [rbx+0BCh]
0x14000e9b9  mov     eax, [r9+2]
0x14000e9bd  bswap   eax
0x14000e9bf  cmp     eax, edx
0x14000e9c1  ja      loc_14000EA54
0x14000e9c7  mov     rcx, [rbx+0F8h]; void *
0x14000e9ce  test    rcx, rcx
0x14000e9d1  jz      short loc_14000E9DE
0x14000e9d3  mov     r8d, edx; Size
0x14000e9d6  mov     rdx, r9; Src
0x14000e9d9  call    memmove
0x14000e9de  mov     ecx, [rbx+0BCh]
0x14000e9e4  mov     rdx, [rbx+0D8h]
0x14000e9eb  test    rdx, rdx
0x14000e9ee  jz      short loc_14000EA5D
0x14000e9f0  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14000e9f7  mov     r8d, edi
0x14000e9fa  mov     r9d, ecx
0x14000e9fd  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14000ea04  mov     rax, [rax+848h]
0x14000ea0b  call    _guard_dispatch_icall
0x14000ea10  mov     qword ptr [rbx+0D8h], 0
0x14000ea1b  mov     rcx, [rbx+0A8h]; struct Tpm20Resource *
0x14000ea22  test    rcx, rcx
0x14000ea25  jnz     loc_14000EAB7
0x14000ea2b  mov     rcx, rbx; this
0x14000ea2e  call    ??1Tpm20Request@@AEAA@XZ; Tpm20Request::~Tpm20Request(void)
0x14000ea33  lea     rcx, [rbx-10h]; P
0x14000ea37  mov     edx, 506D7054h; Tag
0x14000ea3c  call    cs:__imp_ExFreePoolWithTag
0x14000ea43  nop     dword ptr [rax+rax+00h]
0x14000ea48  mov     rbx, [rsp+38h+arg_0]
0x14000ea4d  add     rsp, 30h
0x14000ea51  pop     rdi
0x14000ea52  retn
0x14000ea54  mov     edi, 80000005h
0x14000ea59  xor     ecx, ecx
0x14000ea5b  jmp     short loc_14000E9E4
0x14000ea5d  mov     rax, [rbx+0E0h]
0x14000ea64  mov     [rax+20h], edi
0x14000ea67  mov     rax, [rbx+0E0h]
0x14000ea6e  mov     [rax+24h], ecx
0x14000ea71  mov     rcx, [rbx+0E0h]; Event
0x14000ea78  mov     rax, [rcx+18h]
0x14000ea7c  test    rax, rax
0x14000ea7f  jz      short loc_14000EA93
0x14000ea81  call    _guard_dispatch_icall
0x14000ea86  mov     qword ptr [rbx+0E0h], 0
0x14000ea91  jmp     short loc_14000EA1B
0x14000ea93  xor     r8d, r8d; Wait
0x14000ea96  xor     edx, edx; Increment
0x14000ea98  call    cs:__imp_KeSetEvent
0x14000ea9f  nop     dword ptr [rax+rax+00h]
0x14000eaa4  jmp     short loc_14000EA86
0x14000eaa6  mov     edx, 909h; unsigned int
0x14000eaab  call    ?FormatTpm20Error@Tpm20Request@@QEAAXI@Z; Tpm20Request::FormatTpm20Error(uint)
0x14000eab0  xor     edi, edi
0x14000eab2  jmp     loc_14000E9AF
0x14000eab7  call    ?DeleteTpm20Resource@Tpm20Context@@CAXPEAVTpm20Resource@@@Z; Tpm20Context::DeleteTpm20Resource(Tpm20Resource *)
0x14000eabc  mov     qword ptr [rbx+0A8h], 0
0x14000eac7  jmp     loc_14000EA2B
```
