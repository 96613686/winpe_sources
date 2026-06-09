# TpmTransportSpbI2CDevice::I2CReadRegister(uchar,uchar *,uint,_LARGE_INTEGER,bool)

- ea: `0x140025724`
- end: `0x14002582d`
- name: `?I2CReadRegister@TpmTransportSpbI2CDevice@@IEAAJEPEAEIT_LARGE_INTEGER@@_N@Z`
- size: `265`
- prototype: `__int64 __fastcall(TpmTransportSpbI2CDevice *__hidden this, unsigned __int8, unsigned __int8 *, unsigned int, union _LARGE_INTEGER, bool)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140025480`
- `0x140025880`
- `0x140025938`
- `0x140025960`
- `0x140025a54`
- `0x140025f70`

## callees

- `0x140025724`
- `0x1400268c8`
- `0x140026a68`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x140025762`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400257bd`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140025807`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140025762`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400257bd`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140025807`

## pseudocode

```c
__int64 __fastcall TpmTransportSpbI2CDevice::I2CReadRegister(
        TpmTransportSpbI2CDevice *this,
        char a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  char v4; // al
  __int64 v8; // rbx
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // esi
  __int64 v12; // rbx
  unsigned int i; // ebx
  __int64 v14; // rbx
  char v16; // [rsp+68h] [rbp+10h] BYREF

  v16 = a2;
  v4 = *((_BYTE *)this + 40);
  if ( v4 == 114 && *((_BYTE *)this + 26) || v4 == 119 && *((_BYTE *)this + 27) )
  {
    do
      v8 = MEMORY[0xFFFFF78000000320];
    while ( *((_QWORD *)this + 4) + *((_QWORD *)this + 6) - v8 * KeQueryTimeIncrement() > 0 );
  }
  *((_BYTE *)this + 40) = 119;
  v9 = 0;
  while ( 1 )
  {
    v10 = TpmTransportSpbDevice::SPBWrite(this, &v16, 1u);
    v11 = v10;
    if ( v10 != -1073741810 )
      break;
    if ( (unsigned int)++v9 > 5 )
      goto LABEL_16;
  }
  if ( v10 >= 0 )
  {
    if ( *((_BYTE *)this + 25) )
    {
      do
        v12 = MEMORY[0xFFFFF78000000320];
      while ( *((_QWORD *)this + 4) + *((_QWORD *)this + 6) - v12 * KeQueryTimeIncrement() > 0 );
    }
    *((_BYTE *)this + 40) = 114;
    for ( i = 0; i <= 5; ++i )
    {
      v11 = TpmTransportSpbDevice::SPBRead(this, a3, a4);
      if ( v11 != -1073741810 )
        break;
    }
  }
LABEL_16:
  v14 = MEMORY[0xFFFFF78000000320];
  *((_QWORD *)this + 6) = v14 * KeQueryTimeIncrement();
  return v11;
}

```

## disassembly

```asm
0x140025724  mov     [rsp+arg_8], dl
0x140025728  push    rbx
0x140025729  push    rbp
0x14002572a  push    rsi
0x14002572b  push    rdi
0x14002572c  push    r13
0x14002572e  push    r14
0x140025730  sub     rsp, 28h
0x140025734  mov     al, [rcx+28h]
0x140025737  mov     ebp, r9d
0x14002573a  mov     r14, r8
0x14002573d  mov     rdi, rcx
0x140025740  mov     r13, 0FFFFF78000000320h
0x14002574a  cmp     al, 72h ; 'r'
0x14002574c  jnz     short loc_140025754
0x14002574e  cmp     byte ptr [rcx+1Ah], 0
0x140025752  jnz     short loc_14002575E
0x140025754  cmp     al, 77h ; 'w'
0x140025756  jnz     short loc_140025784
0x140025758  cmp     byte ptr [rcx+1Bh], 0
0x14002575c  jz      short loc_140025784
0x14002575e  mov     rbx, [r13+0]
0x140025762  call    cs:__imp_KeQueryTimeIncrement
0x140025769  nop     dword ptr [rax+rax+00h]
0x14002576e  mov     rcx, [rdi+30h]
0x140025772  mov     eax, eax
0x140025774  imul    rax, rbx
0x140025778  sub     rcx, rax
0x14002577b  add     rcx, [rdi+20h]
0x14002577f  test    rcx, rcx
0x140025782  jg      short loc_14002575E
0x140025784  mov     byte ptr [rdi+28h], 77h ; 'w'
0x140025788  xor     ebx, ebx
0x14002578a  mov     r8d, 1; unsigned int
0x140025790  lea     rdx, [rsp+58h+arg_8]; void *
0x140025795  mov     rcx, rdi; this
0x140025798  call    ?SPBWrite@TpmTransportSpbDevice@@IEAAJPEAXI@Z; TpmTransportSpbDevice::SPBWrite(void *,uint)
0x14002579d  mov     esi, eax
0x14002579f  cmp     eax, 0C000000Eh
0x1400257a4  jnz     short loc_1400257AF
0x1400257a6  inc     ebx
0x1400257a8  cmp     ebx, 5
0x1400257ab  jbe     short loc_14002578A
0x1400257ad  jmp     short loc_140025803
0x1400257af  test    eax, eax
0x1400257b1  js      short loc_140025803
0x1400257b3  cmp     byte ptr [rdi+19h], 0
0x1400257b7  jz      short loc_1400257DF
0x1400257b9  mov     rbx, [r13+0]
0x1400257bd  call    cs:__imp_KeQueryTimeIncrement
0x1400257c4  nop     dword ptr [rax+rax+00h]
0x1400257c9  mov     rcx, [rdi+30h]
0x1400257cd  mov     eax, eax
0x1400257cf  imul    rax, rbx
0x1400257d3  sub     rcx, rax
0x1400257d6  add     rcx, [rdi+20h]
0x1400257da  test    rcx, rcx
0x1400257dd  jg      short loc_1400257B9
0x1400257df  mov     byte ptr [rdi+28h], 72h ; 'r'
0x1400257e3  xor     ebx, ebx
0x1400257e5  mov     r8d, ebp; unsigned int
0x1400257e8  mov     rdx, r14; void *
0x1400257eb  mov     rcx, rdi; this
0x1400257ee  call    ?SPBRead@TpmTransportSpbDevice@@IEAAJPEAXI@Z; TpmTransportSpbDevice::SPBRead(void *,uint)
0x1400257f3  mov     esi, eax
0x1400257f5  cmp     eax, 0C000000Eh
0x1400257fa  jnz     short loc_140025803
0x1400257fc  inc     ebx
0x1400257fe  cmp     ebx, 5
0x140025801  jbe     short loc_1400257E5
0x140025803  mov     rbx, [r13+0]
0x140025807  call    cs:__imp_KeQueryTimeIncrement
0x14002580e  nop     dword ptr [rax+rax+00h]
0x140025813  mov     eax, eax
0x140025815  imul    rax, rbx
0x140025819  mov     [rdi+30h], rax
0x14002581d  mov     eax, esi
0x14002581f  add     rsp, 28h
0x140025823  pop     r14
0x140025825  pop     r13
0x140025827  pop     rdi
0x140025828  pop     rsi
0x140025829  pop     rbp
0x14002582a  pop     rbx
0x14002582b  retn
```
