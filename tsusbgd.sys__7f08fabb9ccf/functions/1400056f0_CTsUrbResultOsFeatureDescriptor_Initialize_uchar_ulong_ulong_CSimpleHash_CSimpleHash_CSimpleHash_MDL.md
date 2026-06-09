# CTsUrbResultOsFeatureDescriptor::Initialize(uchar *,ulong,ulong,CSimpleHash *,CSimpleHash *,CSimpleHash *,_MDL *)

- ea: `0x1400056f0`
- end: `0x1400057c6`
- name: `?Initialize@CTsUrbResultOsFeatureDescriptor@@EEAAJPEAEKKPEAVCSimpleHash@@11PEAU_MDL@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(CTsUrbResultOsFeatureDescriptor *this, unsigned __int8 *, int, unsigned int, struct CSimpleHash *, struct CSimpleHash *, struct CSimpleHash *, struct _MDL *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x14000491c`
- `0x1400056f0`
- `0x140006440`

## pseudocode

```c
__int64 __fastcall CTsUrbResultOsFeatureDescriptor::Initialize(
        CTsUrbResultOsFeatureDescriptor *this,
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

  if ( !a8 || a3 != 16 || *(_WORD *)a2 != 16 || a4 < 8 )
    return 3221225485LL;
  Urb = CTsUrbResult::AllocateUrb(this, 0x88u);
  v12 = Urb;
  if ( !Urb )
    return 3221225495LL;
  memset(&Urb->UrbSelectInterface.Hdr.Function, 0, 0x86u);
  v12->UrbHeader.Length = 136;
  v12->UrbHeader.Function = *((_WORD *)a2 + 1);
  v12->UrbControlTransfer.SetupPacket[0] ^= (a2[8] ^ v12->UrbControlTransfer.SetupPacket[0]) & 0x1F;
  v12->UrbControlTransfer.SetupPacket[2] = a2[9];
  v12->UrbControlTransfer.SetupPacket[3] = a2[10];
  v12->UrbControlDescriptorRequest.LanguageId = *((_WORD *)a2 + 6);
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
0x1400056f0  push    rbx
0x1400056f2  push    rbp
0x1400056f3  push    rsi
0x1400056f4  push    rdi
0x1400056f5  push    r14
0x1400056f7  push    r15
0x1400056f9  sub     rsp, 28h
0x1400056fd  mov     rsi, [rsp+58h+arg_38]
0x140005705  mov     rdi, rdx
0x140005708  mov     rbp, rcx
0x14000570b  test    rsi, rsi
0x14000570e  jnz     short loc_14000571A
0x140005710  mov     eax, 0C000000Dh
0x140005715  jmp     loc_1400057B8
0x14000571a  mov     eax, 10h
0x14000571f  cmp     r8d, eax
0x140005722  jnz     short loc_140005710
0x140005724  cmp     [rdx], ax
0x140005727  jnz     short loc_140005710
0x140005729  lea     r14d, [rax-8]
0x14000572d  cmp     r9d, r14d
0x140005730  jb      short loc_140005710
0x140005732  lea     r15d, [rax+78h]
0x140005736  mov     edx, r15d; unsigned int
0x140005739  call    ?AllocateUrb@CTsUrbResult@@IEAAPEAU_URB@@K@Z; CTsUrbResult::AllocateUrb(ulong)
0x14000573e  mov     rbx, rax
0x140005741  test    rax, rax
0x140005744  jnz     short loc_14000574D
0x140005746  mov     eax, 0C0000017h
0x14000574b  jmp     short loc_1400057B8
0x14000574d  lea     rcx, [rax+2]; void *
0x140005751  xor     edx, edx; Val
0x140005753  mov     r8d, 86h; Size
0x140005759  call    memset
0x14000575e  mov     [rbx], r15w
0x140005762  movzx   eax, word ptr [rdi+2]
0x140005766  mov     [rbx+2], ax
0x14000576a  mov     al, [rbx+80h]
0x140005770  mov     cl, al
0x140005772  xor     cl, [rdi+8]
0x140005775  and     cl, 1Fh
0x140005778  xor     cl, al
0x14000577a  mov     [rbx+80h], cl
0x140005780  mov     al, [rdi+9]
0x140005783  mov     [rbx+82h], al
0x140005789  mov     al, [rdi+0Ah]
0x14000578c  mov     [rbx+83h], al
0x140005792  movzx   eax, word ptr [rdi+0Ch]
0x140005796  mov     [rbx+84h], ax
0x14000579d  mov     [rbx+30h], rsi
0x1400057a1  mov     eax, [rsi+28h]
0x1400057a4  mov     [rbx+24h], eax
0x1400057a7  xor     eax, eax
0x1400057a9  mov     [rbp+6B0h], rsi
0x1400057b0  mov     [rbp+6AAh], r14w
0x1400057b8  add     rsp, 28h
0x1400057bc  pop     r15
0x1400057be  pop     r14
0x1400057c0  pop     rdi
0x1400057c1  pop     rsi
0x1400057c2  pop     rbp
0x1400057c3  pop     rbx
0x1400057c4  retn
```
