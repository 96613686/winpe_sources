# UwfServicingRegGetMultiString(HKEY__ *,ushort const *,ushort const *,ushort *,long *,ushort * *,long *)

- ea: `0x180002db0`
- end: `0x180002f0e`
- name: `?UwfServicingRegGetMultiString@@YAJPEAUHKEY__@@PEBG1PEAGPEAJPEAPEAG3@Z`
- size: `350`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, int *, unsigned __int16 **, int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180003d68`
- `0x180004008`
- `0x18000422c`
- `0x1800043f4`

## callees

- `0x1800024f6`
- `0x180002db0`
- `0x180002f14`

## import_xrefs

- `msvcrt!free` at `0x180002e68`
- `msvcrt!free` at `0x180002ea0`
- `msvcrt!free` at `0x180002e68`
- `msvcrt!free` at `0x180002ea0`

## string_xrefs

- `0x180002e12`: `SYSTEM\CurrentControlSet\Services\UwfServicingSvc\Servicing\Config\UpdateAgent`

## pseudocode

```c
LSTATUS __fastcall UwfServicingRegGetMultiString(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        int *a5,
        unsigned __int16 **a6,
        int *a7)
{
  int *v7; // r14
  int *v9; // rdi
  LSTATUS result; // eax
  int v11; // r8d
  _WORD *v12; // rcx
  unsigned int v13; // r10d
  bool v14; // zf
  unsigned int v15; // r9d
  int v16; // edx
  signed int v17; // ebx
  void *v18; // rdx
  unsigned __int16 **v19; // r9
  int v20; // edx
  int v21; // r8d
  __int64 v22; // rax
  void *Block; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v24; // [rsp+60h] [rbp+8h] BYREF
  int v25; // [rsp+64h] [rbp+Ch]
  unsigned int v26; // [rsp+68h] [rbp+10h] BYREF
  int v27; // [rsp+6Ch] [rbp+14h]

  v27 = HIDWORD(a2);
  v25 = HIDWORD(a1);
  v7 = a7;
  v24 = 7;
  v26 = 0;
  Block = 0;
  if ( a7 )
  {
    v9 = a5;
    if ( a5 )
    {
      result = UwfServicingRegGetValue(
                 a1,
                 L"SYSTEM\\CurrentControlSet\\Services\\UwfServicingSvc\\Servicing\\Config\\UpdateAgent",
                 a3,
                 &v24,
                 &Block,
                 &v26);
      if ( result < 0 )
        return result;
      if ( !a4 )
      {
        v11 = 0;
        v12 = Block;
        v13 = 0;
        v14 = v26 >> 1 == 0;
        v15 = v26 >> 1;
        *v9 = v26 >> 1;
        if ( !v14 )
        {
          do
          {
            v16 = v11 + 1;
            if ( v12[v13] )
              v16 = v11;
            ++v13;
            v11 = v16;
          }
          while ( v13 < v15 );
        }
        *v7 = v11 - 1;
        free(v12);
        return 0;
      }
      v17 = v26 >> 1;
      if ( *v9 <= (int)(v26 >> 1) )
        v17 = *v9;
      else
        *v9 = v17;
      v18 = Block;
      *a4 = 0;
      memcpy_0(a4, v18, 2LL * v17);
      free(Block);
      v19 = a6;
      if ( a6 )
      {
        *a6 = a4;
        v20 = 0;
        v21 = 1;
        while ( v20 < v17 - 1 )
        {
          if ( a4[v20] )
          {
            ++v20;
          }
          else
          {
            if ( v21 >= *v7 )
              return 0;
            ++v20;
            v22 = v21++;
            v19[v22] = &a4[v20];
          }
        }
        return 0;
      }
    }
  }
  return -2147024809;
}

```

## disassembly

```asm
0x180002db0  mov     r11, rsp
0x180002db3  mov     [r11+18h], rbx
0x180002db7  mov     [r11+20h], rbp
0x180002dbb  mov     [r11+10h], rdx
0x180002dbf  mov     [r11+8], rcx
0x180002dc3  push    rsi
0x180002dc4  push    rdi
0x180002dc5  push    r14
0x180002dc7  sub     rsp, 40h
0x180002dcb  mov     r14, [rsp+58h+arg_30]
0x180002dd3  xor     ebp, ebp
0x180002dd5  mov     [rsp+58h+arg_0], 7
0x180002ddd  mov     rsi, r9
0x180002de0  mov     [rsp+58h+arg_8], ebp
0x180002de4  mov     [r11-28h], rbp
0x180002de8  test    r14, r14
0x180002deb  jz      loc_180002EF6
0x180002df1  mov     rdi, [rsp+58h+arg_20]
0x180002df9  test    rdi, rdi
0x180002dfc  jz      loc_180002EF6
0x180002e02  lea     rax, [r11+10h]
0x180002e06  mov     [r11-30h], rax
0x180002e0a  lea     r9, [r11+8]; unsigned int *
0x180002e0e  lea     rax, [r11-28h]
0x180002e12  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\Uw"...
0x180002e19  mov     [r11-38h], rax
0x180002e1d  call    ?UwfServicingRegGetValue@@YAJPEAUHKEY__@@PEBG1PEAKPEAPEAX2@Z; UwfServicingRegGetValue(HKEY__ *,ushort const *,ushort const *,ulong *,void * *,ulong *)
0x180002e22  test    eax, eax
0x180002e24  js      loc_180002EFB
0x180002e2a  test    rsi, rsi
0x180002e2d  jnz     short loc_180002E75
0x180002e2f  mov     r9d, [rsp+58h+arg_8]
0x180002e34  mov     r8d, ebp
0x180002e37  mov     rcx, [rsp+58h+Block]; Block
0x180002e3c  mov     r10d, ebp
0x180002e3f  shr     r9d, 1
0x180002e42  mov     [rdi], r9d
0x180002e45  jz      short loc_180002E61
0x180002e47  mov     eax, r10d
0x180002e4a  lea     edx, [r8+1]
0x180002e4e  cmp     [rcx+rax*2], bp
0x180002e52  cmovnz  edx, r8d
0x180002e56  inc     r10d
0x180002e59  mov     r8d, edx
0x180002e5c  cmp     r10d, r9d
0x180002e5f  jb      short loc_180002E47
0x180002e61  lea     eax, [r8-1]
0x180002e65  mov     [r14], eax
0x180002e68  call    cs:__imp_free
0x180002e6e  xor     eax, eax
0x180002e70  jmp     loc_180002EFB
0x180002e75  mov     ebx, [rsp+58h+arg_8]
0x180002e79  shr     ebx, 1
0x180002e7b  cmp     [rdi], ebx
0x180002e7d  jle     short loc_180002E83
0x180002e7f  mov     [rdi], ebx
0x180002e81  jmp     short loc_180002E85
0x180002e83  mov     ebx, [rdi]
0x180002e85  mov     rdx, [rsp+58h+Block]; Src
0x180002e8a  mov     rcx, rsi; void *
0x180002e8d  movsxd  r8, ebx
0x180002e90  add     r8, r8; Size
0x180002e93  mov     [rsi], bp
0x180002e96  call    memcpy_0
0x180002e9b  mov     rcx, [rsp+58h+Block]; Block
0x180002ea0  call    cs:__imp_free
0x180002ea6  mov     r9, [rsp+58h+arg_28]
0x180002eae  test    r9, r9
0x180002eb1  jz      short loc_180002EF6
0x180002eb3  lea     eax, [rbx-1]
0x180002eb6  mov     [r9], rsi
0x180002eb9  mov     edx, ebp
0x180002ebb  mov     r8d, 1
0x180002ec1  test    eax, eax
0x180002ec3  jle     short loc_180002E6E
0x180002ec5  movsxd  rcx, edx
0x180002ec8  cmp     bp, [rsi+rcx*2]
0x180002ecc  jnz     short loc_180002EE8
0x180002ece  cmp     r8d, [r14]
0x180002ed1  jge     short loc_180002E6E
0x180002ed3  inc     edx
0x180002ed5  movsxd  rax, edx
0x180002ed8  lea     rcx, [rsi+rax*2]
0x180002edc  movsxd  rax, r8d
0x180002edf  inc     r8d
0x180002ee2  mov     [r9+rax*8], rcx
0x180002ee6  jmp     short loc_180002EEA
0x180002ee8  inc     edx
0x180002eea  lea     eax, [rbx-1]
0x180002eed  cmp     edx, eax
0x180002eef  jl      short loc_180002EC5
0x180002ef1  jmp     loc_180002E6E
0x180002ef6  mov     eax, 80070057h
0x180002efb  mov     rbx, [rsp+58h+arg_10]
0x180002f00  mov     rbp, [rsp+58h+arg_18]
0x180002f05  add     rsp, 40h
0x180002f09  pop     r14
0x180002f0b  pop     rdi
0x180002f0c  pop     rsi
0x180002f0d  retn
```
