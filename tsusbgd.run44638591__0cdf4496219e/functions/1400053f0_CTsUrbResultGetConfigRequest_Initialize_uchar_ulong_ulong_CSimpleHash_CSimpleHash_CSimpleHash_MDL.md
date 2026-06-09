# CTsUrbResultGetConfigRequest::Initialize(uchar *,ulong,ulong,CSimpleHash *,CSimpleHash *,CSimpleHash *,_MDL *)

- ea: `0x1400053f0`
- end: `0x140005490`
- name: `?Initialize@CTsUrbResultGetConfigRequest@@EEAAJPEAEKKPEAVCSimpleHash@@11PEAU_MDL@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(CTsUrbResultGetConfigRequest *__hidden this, unsigned __int8 *, unsigned int, unsigned int, struct CSimpleHash *, struct CSimpleHash *, struct CSimpleHash *, struct _MDL *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x14000491c`
- `0x1400053f0`
- `0x140006440`

## pseudocode

```c
__int64 __fastcall CTsUrbResultGetConfigRequest::Initialize(
        CTsUrbResultGetConfigRequest *this,
        unsigned __int8 *a2,
        int a3,
        unsigned int a4,
        struct CSimpleHash *a5,
        struct CSimpleHash *a6,
        struct CSimpleHash *a7,
        struct _MDL *a8)
{
  __int64 result; // rax
  struct _URB *Urb; // rax
  struct _URB *v12; // rbx

  if ( !a8 || a3 != 8 || *(_WORD *)a2 != 8 || a4 < 8 )
    return 3221225485LL;
  Urb = CTsUrbResult::AllocateUrb(this, 0x88u);
  v12 = Urb;
  if ( !Urb )
    return 3221225495LL;
  memset(&Urb->UrbSelectInterface.Hdr.Function, 0, 0x86u);
  v12->UrbHeader.Length = 136;
  v12->UrbHeader.Function = *((_WORD *)a2 + 1);
  v12->UrbSelectConfiguration.Interface.InterfaceHandle = a8;
  v12->UrbControlTransfer.TransferBufferLength = a8->ByteCount;
  result = 0;
  *((_QWORD *)this + 214) = a8;
  *((_WORD *)this + 853) = 8;
  return result;
}

```

## disassembly

```asm
0x1400053f0  push    rbx
0x1400053f2  push    rbp
0x1400053f3  push    rsi
0x1400053f4  push    rdi
0x1400053f5  push    r14
0x1400053f7  push    r15
0x1400053f9  sub     rsp, 28h
0x1400053fd  mov     rdi, [rsp+58h+arg_38]
0x140005405  mov     rbp, rdx
0x140005408  mov     rsi, rcx
0x14000540b  test    rdi, rdi
0x14000540e  jnz     short loc_140005417
0x140005410  mov     eax, 0C000000Dh
0x140005415  jmp     short loc_140005482
0x140005417  mov     r14d, 8
0x14000541d  cmp     r8d, r14d
0x140005420  jnz     short loc_140005410
0x140005422  cmp     [rdx], r14w
0x140005426  jnz     short loc_140005410
0x140005428  cmp     r9d, r14d
0x14000542b  jb      short loc_140005410
0x14000542d  mov     r15d, 88h
0x140005433  mov     edx, r15d; unsigned int
0x140005436  call    ?AllocateUrb@CTsUrbResult@@IEAAPEAU_URB@@K@Z; CTsUrbResult::AllocateUrb(ulong)
0x14000543b  mov     rbx, rax
0x14000543e  test    rax, rax
0x140005441  jnz     short loc_14000544A
0x140005443  mov     eax, 0C0000017h
0x140005448  jmp     short loc_140005482
0x14000544a  lea     rcx, [rax+2]; void *
0x14000544e  xor     edx, edx; Val
0x140005450  mov     r8d, 86h; Size
0x140005456  call    memset
0x14000545b  mov     [rbx], r15w
0x14000545f  movzx   eax, word ptr [rbp+2]
0x140005463  mov     [rbx+2], ax
0x140005467  mov     [rbx+30h], rdi
0x14000546b  mov     eax, [rdi+28h]
0x14000546e  mov     [rbx+24h], eax
0x140005471  xor     eax, eax
0x140005473  mov     [rsi+6B0h], rdi
0x14000547a  mov     [rsi+6AAh], r14w
0x140005482  add     rsp, 28h
0x140005486  pop     r15
0x140005488  pop     r14
0x14000548a  pop     rdi
0x14000548b  pop     rsi
0x14000548c  pop     rbp
0x14000548d  pop     rbx
0x14000548e  retn
```
