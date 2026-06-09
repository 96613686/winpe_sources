# tpm12class::TPMW8_COMMAND::AddHandle(uint,tpm12class::TPMW82B_BUFFER *)

- ea: `0x140035488`
- end: `0x1400355bb`
- name: `?AddHandle@TPMW8_COMMAND@tpm12class@@QEAAJIPEAVTPMW82B_BUFFER@2@@Z`
- size: `307`
- prototype: `int(tpm12class::TPMW8_COMMAND *__hidden this, unsigned int, struct tpm12class::TPMW82B_BUFFER *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400389a0`
- `0x140038ee0`

## callees

- `0x14000cb50`
- `0x14000cdf4`
- `0x140031554`
- `0x140031d2c`
- `0x140035488`
- `0x140039b40`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_COMMAND::AddHandle(
        tpm12class::TPMW8_COMMAND *this,
        unsigned int a2,
        unsigned __int8 **a3)
{
  unsigned int v6; // eax
  int v8; // ebx
  unsigned __int8 *v9; // rcx
  unsigned __int8 *v10; // rax

  v6 = a2 & 0xFF000000;
  if ( (a2 & 0xFF000000) == 0 || v6 == 0x2000000 || v6 == 50331648 || v6 == 0x40000000 )
  {
    v8 = tpm12class::TpmDataObject::AddData(this, a2);
    if ( v8 < 0 )
      return (unsigned int)v8;
    v8 = tpm12class::TPMW82B_BUFFER::Empty((tpm12class::TPMW82B_BUFFER *)a3);
    if ( v8 < 0 )
      return (unsigned int)v8;
    v9 = a3[8];
    *((_WORD *)a3 + 28) = 4;
    if ( v9 )
    {
      TpmFree(v9);
      a3[8] = 0;
    }
    v10 = (unsigned __int8 *)operator new(*((unsigned __int16 *)a3 + 28));
    a3[8] = v10;
    if ( v10 )
    {
      memset(v10, 0, *((unsigned __int16 *)a3 + 28));
      *a3[8] = HIBYTE(a2);
      a3[8][1] = BYTE2(a2);
      a3[8][2] = BYTE1(a2);
      a3[8][3] = a2;
LABEL_19:
      ++*((_DWORD *)this + 21);
      return (unsigned int)v8;
    }
    return (unsigned int)-2147024888;
  }
  else
  {
    if ( v6 != 0x1000000 && v6 != 0x80000000 && v6 != -2130706432 )
      return 2147942413LL;
    *((_BYTE *)this + 48) = 1;
    v8 = tpm12class::TpmDataObject::AddData(this, a2);
    if ( v8 >= 0 )
    {
      *((_BYTE *)this + 48) = 0;
      v8 = tpm12class::TpmDataObject::AddDataToBuffer(
             (tpm12class::TPMW8_COMMAND *)((char *)this + 40),
             a3[8],
             *((unsigned __int16 *)a3 + 28),
             (unsigned __int8 **)this + 4,
             (unsigned int *)this + 10,
             (unsigned int *)this + 11);
      if ( v8 >= 0 )
        goto LABEL_19;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140035488  push    rbx
0x14003548a  push    rbp
0x14003548b  push    rsi
0x14003548c  push    rdi
0x14003548d  sub     rsp, 38h
0x140035491  mov     eax, edx
0x140035493  mov     rdi, r8
0x140035496  mov     ebp, edx
0x140035498  mov     rsi, rcx
0x14003549b  and     eax, 0FF000000h
0x1400354a0  jz      short loc_140035520
0x1400354a2  cmp     eax, 2000000h
0x1400354a7  jz      short loc_140035520
0x1400354a9  cmp     eax, 3000000h
0x1400354ae  jz      short loc_140035520
0x1400354b0  cmp     eax, 40000000h
0x1400354b5  jz      short loc_140035520
0x1400354b7  cmp     eax, 1000000h
0x1400354bc  jz      short loc_1400354D6
0x1400354be  cmp     eax, 80000000h
0x1400354c3  jz      short loc_1400354D6
0x1400354c5  cmp     eax, 81000000h
0x1400354ca  jz      short loc_1400354D6
0x1400354cc  mov     eax, 8007000Dh
0x1400354d1  jmp     loc_1400355B1
0x1400354d6  mov     byte ptr [rcx+30h], 1
0x1400354da  call    ?AddData@TpmDataObject@tpm12class@@QEAAJI@Z; tpm12class::TpmDataObject::AddData(uint)
0x1400354df  mov     ebx, eax
0x1400354e1  test    eax, eax
0x1400354e3  js      loc_1400355AF
0x1400354e9  mov     byte ptr [rsi+30h], 0
0x1400354ed  lea     rax, [rsi+2Ch]
0x1400354f1  movzx   r8d, word ptr [rdi+38h]; unsigned int
0x1400354f6  lea     rcx, [rsi+28h]; this
0x1400354fa  mov     rdx, [rdi+40h]; unsigned __int8 *
0x1400354fe  lea     r9, [rsi+20h]; unsigned __int8 **
0x140035502  mov     [rsp+58h+var_30], rax; unsigned int *
0x140035507  mov     [rsp+58h+var_38], rcx; unsigned int *
0x14003550c  call    ?AddDataToBuffer@TpmDataObject@tpm12class@@AEAAJPEAEIPEAPEAEPEAI2@Z; tpm12class::TpmDataObject::AddDataToBuffer(uchar *,uint,uchar * *,uint *,uint *)
0x140035511  mov     ebx, eax
0x140035513  test    eax, eax
0x140035515  js      loc_1400355AF
0x14003551b  jmp     loc_1400355AC
0x140035520  call    ?AddData@TpmDataObject@tpm12class@@QEAAJI@Z; tpm12class::TpmDataObject::AddData(uint)
0x140035525  mov     ebx, eax
0x140035527  test    eax, eax
0x140035529  js      loc_1400355AF
0x14003552f  mov     rcx, rdi; this
0x140035532  call    ?Empty@TPMW82B_BUFFER@tpm12class@@QEAAJXZ; tpm12class::TPMW82B_BUFFER::Empty(void)
0x140035537  mov     ebx, eax
0x140035539  test    eax, eax
0x14003553b  js      short loc_1400355AF
0x14003553d  mov     rcx, [rdi+40h]; void *
0x140035541  mov     word ptr [rdi+38h], 4
0x140035547  test    rcx, rcx
0x14003554a  jz      short loc_140035559
0x14003554c  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140035551  mov     qword ptr [rdi+40h], 0
0x140035559  movzx   ecx, word ptr [rdi+38h]; unsigned __int64
0x14003555d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140035562  mov     [rdi+40h], rax
0x140035566  test    rax, rax
0x140035569  jnz     short loc_140035572
0x14003556b  mov     ebx, 80070008h
0x140035570  jmp     short loc_1400355AF
0x140035572  movzx   r8d, word ptr [rdi+38h]; Size
0x140035577  xor     edx, edx; Val
0x140035579  mov     rcx, rax; void *
0x14003557c  call    memset
0x140035581  mov     rax, [rdi+40h]
0x140035585  mov     ecx, ebp
0x140035587  shr     ecx, 18h
0x14003558a  mov     [rax], cl
0x14003558c  mov     ecx, ebp
0x14003558e  mov     rax, [rdi+40h]
0x140035592  shr     ecx, 10h
0x140035595  mov     [rax+1], cl
0x140035598  mov     ecx, ebp
0x14003559a  mov     rax, [rdi+40h]
0x14003559e  shr     ecx, 8
0x1400355a1  mov     [rax+2], cl
0x1400355a4  mov     rax, [rdi+40h]
0x1400355a8  mov     [rax+3], bpl
0x1400355ac  inc     dword ptr [rsi+54h]
0x1400355af  mov     eax, ebx
0x1400355b1  add     rsp, 38h
0x1400355b5  pop     rdi
0x1400355b6  pop     rsi
0x1400355b7  pop     rbp
0x1400355b8  pop     rbx
0x1400355b9  retn
```
