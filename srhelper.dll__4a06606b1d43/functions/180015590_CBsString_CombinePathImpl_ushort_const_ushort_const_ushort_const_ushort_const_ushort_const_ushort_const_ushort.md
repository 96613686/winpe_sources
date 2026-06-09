# CBsString::_CombinePathImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180015590`
- end: `0x180015758`
- name: `?_CombinePathImpl@CBsString@@AEAAJPEBG000000000@Z`
- size: `456`
- prototype: `__int64 __fastcall(CBsString *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b3b0`
- `0x18000bdd0`
- `0x18000bf70`
- `0x18000c468`
- `0x18000c890`
- `0x180015390`

## callees

- `0x1800154c8`
- `0x180015590`
- `0x1800157be`
- `0x1800157f0`

## pseudocode

```c
__int64 __fastcall CBsString::_CombinePathImpl(
        CBsString *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v7; // ebx
  __int64 i; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // r8d
  unsigned int v12; // edx
  __int64 v13; // r10
  BOOL v14; // r9d
  BOOL v15; // r11d
  unsigned __int16 *v16; // r8
  __int64 v17; // rax
  unsigned int v18; // ecx
  __int64 v19; // rax
  unsigned int j; // r9d
  __int64 v21; // rax
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-C0h]
  __int128 v24; // [rsp+50h] [rbp-B0h]
  __int128 v25; // [rsp+60h] [rbp-A0h]
  __int128 v26; // [rsp+70h] [rbp-90h]
  __int128 v27; // [rsp+80h] [rbp-80h]
  _OWORD v28[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+B0h] [rbp-50h]
  unsigned int v30[20]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v31[20]; // [rsp+110h] [rbp+10h] BYREF

  v23[0] = a2;
  v23[1] = a3;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v29 = 0;
  memset(v28, 0, sizeof(v28));
  memset_0(v31, 0, sizeof(v31));
  memset_0(v30, 0, sizeof(v30));
  v22 = 92;
  if ( !a2 )
    return 2147942487LL;
  v7 = 0;
  for ( i = 0; i != 10; ++i )
  {
    v9 = v23[i];
    if ( v9 )
    {
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)(v9 + 2 * v10) );
    }
    else
    {
      LODWORD(v10) = 0;
    }
    *((_DWORD *)v28 + i) = v10;
  }
  v11 = *((_DWORD *)this + 2);
  v12 = 0;
  LODWORD(v13) = 0;
  v14 = 0;
  if ( v11 )
    LOBYTE(v14) = *(_WORD *)(*(_QWORD *)this + 2LL * (unsigned int)(v11 - 1)) == 92;
  v15 = v11 == 0;
  do
  {
    v16 = (unsigned __int16 *)v23[(unsigned int)v13];
    if ( v14 && *v16 == 92 )
    {
      ++v16;
      --*((_DWORD *)v28 + (unsigned int)v13);
    }
    else if ( !v15 && !v14 && *v16 != 92 )
    {
      v17 = v12++;
      v31[v17] = (unsigned __int16 *)&v22;
      v30[v17] = 1;
    }
    v18 = *((_DWORD *)v28 + (unsigned int)v13);
    v19 = v12++;
    v31[v19] = v16;
    v30[v19] = v18;
    v14 = v16[v18 - 1] == 92;
    v13 = (unsigned int)(v13 + 1);
    if ( (unsigned int)v13 >= 0xA )
      break;
    v15 = 0;
  }
  while ( *((_DWORD *)v28 + v13) );
  for ( j = 0; j < v12; v7 += v30[v21] )
    v21 = j++;
  return CBsString::_Append(this, v12, v7, v30, (const unsigned __int16 **const)v31);
}

```

## disassembly

```asm
0x180015590  mov     [rsp-8+arg_8], rbx
0x180015595  mov     [rsp-8+arg_10], rsi
0x18001559a  push    rbp
0x18001559b  push    rdi
0x18001559c  push    r14
0x18001559e  lea     rbp, [rsp-0C0h]
0x1800155a6  sub     rsp, 1C0h
0x1800155ad  mov     rax, cs:__security_cookie
0x1800155b4  xor     rax, rsp
0x1800155b7  mov     [rbp+0D0h+var_20], rax
0x1800155be  xorps   xmm0, xmm0
0x1800155c1  mov     [rsp+1D0h+var_190], rdx
0x1800155c6  xorps   xmm1, xmm1
0x1800155c9  mov     [rsp+1D0h+var_188], r8
0x1800155ce  mov     rbx, rdx
0x1800155d1  movdqa  [rsp+1D0h+var_180], xmm0
0x1800155d7  mov     rdi, rcx
0x1800155da  movdqa  [rsp+1D0h+var_170], xmm1
0x1800155e0  xor     eax, eax
0x1800155e2  movdqa  [rsp+1D0h+var_160], xmm0
0x1800155e8  xor     edx, edx; Val
0x1800155ea  movdqa  [rbp+0D0h+var_150], xmm1
0x1800155ef  mov     r8d, 0A0h; Size
0x1800155f5  mov     [rbp+0D0h+var_120], rax
0x1800155f9  lea     rcx, [rbp+0D0h+var_C0]; void *
0x1800155fd  movups  [rbp+0D0h+var_140], xmm0
0x180015601  movups  [rbp+0D0h+var_130], xmm0
0x180015605  call    memset_0
0x18001560a  xor     edx, edx; Val
0x18001560c  lea     rcx, [rbp+0D0h+var_110]; void *
0x180015610  lea     r8d, [rdx+50h]; Size
0x180015614  call    memset_0
0x180015619  xor     esi, esi
0x18001561b  mov     r14d, 5Ch ; '\'
0x180015621  mov     [rsp+1D0h+var_1A0], r14d
0x180015626  test    rbx, rbx
0x180015629  jnz     short loc_180015635
0x18001562b  mov     eax, 80070057h
0x180015630  jmp     loc_180015731
0x180015635  mov     ebx, esi
0x180015637  mov     rax, rsi
0x18001563a  mov     rdx, [rsp+rax*8+1D0h+var_190]
0x18001563f  test    rdx, rdx
0x180015642  jnz     short loc_180015648
0x180015644  mov     ecx, esi
0x180015646  jmp     short loc_180015655
0x180015648  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001564c  inc     rcx
0x18001564f  cmp     [rdx+rcx*2], si
0x180015653  jnz     short loc_18001564C
0x180015655  mov     dword ptr [rbp+rax*4+0D0h+var_140], ecx
0x180015659  inc     rax
0x18001565c  cmp     rax, 0Ah
0x180015660  jnz     short loc_18001563A
0x180015662  mov     r8d, [rdi+8]
0x180015666  mov     edx, esi
0x180015668  mov     r10d, esi
0x18001566b  mov     r9d, esi
0x18001566e  test    r8d, r8d
0x180015671  jz      short loc_180015683
0x180015673  mov     rax, [rdi]
0x180015676  lea     ecx, [r8-1]
0x18001567a  cmp     [rax+rcx*2], r14w
0x18001567f  setz    r9b
0x180015683  test    r8d, r8d
0x180015686  mov     r11d, esi
0x180015689  setz    r11b
0x18001568d  mov     ecx, r10d
0x180015690  mov     r8, [rsp+rcx*8+1D0h+var_190]
0x180015695  test    r9d, r9d
0x180015698  jz      short loc_1800156AA
0x18001569a  cmp     [r8], r14w
0x18001569e  jnz     short loc_1800156AA
0x1800156a0  add     r8, 2
0x1800156a4  dec     dword ptr [rbp+rcx*4+0D0h+var_140]
0x1800156a8  jmp     short loc_1800156D0
0x1800156aa  test    r11d, r11d
0x1800156ad  jnz     short loc_1800156D0
0x1800156af  test    r9d, r9d
0x1800156b2  jnz     short loc_1800156D0
0x1800156b4  cmp     [r8], r14w
0x1800156b8  jz      short loc_1800156D0
0x1800156ba  mov     eax, edx
0x1800156bc  lea     r9, [rsp+1D0h+var_1A0]
0x1800156c1  inc     edx
0x1800156c3  mov     [rbp+rax*8+0D0h+var_C0], r9
0x1800156c8  mov     [rbp+rax*4+0D0h+var_110], 1
0x1800156d0  mov     ecx, dword ptr [rbp+rcx*4+0D0h+var_140]
0x1800156d4  mov     r9d, esi
0x1800156d7  mov     eax, edx
0x1800156d9  inc     edx; unsigned int
0x1800156db  mov     [rbp+rax*8+0D0h+var_C0], r8
0x1800156e0  mov     [rbp+rax*4+0D0h+var_110], ecx
0x1800156e4  lea     eax, [rcx-1]
0x1800156e7  cmp     [r8+rax*2], r14w
0x1800156ec  setz    r9b
0x1800156f0  inc     r10d
0x1800156f3  cmp     r10d, 0Ah
0x1800156f7  jnb     short loc_180015703
0x1800156f9  mov     r11d, esi
0x1800156fc  cmp     dword ptr [rbp+r10*4+0D0h+var_140], esi
0x180015701  ja      short loc_18001568D
0x180015703  mov     r9d, esi
0x180015706  test    edx, edx
0x180015708  jz      short loc_180015719
0x18001570a  mov     eax, r9d
0x18001570d  inc     r9d
0x180015710  add     ebx, [rbp+rax*4+0D0h+var_110]
0x180015714  cmp     r9d, edx
0x180015717  jb      short loc_18001570A
0x180015719  lea     rax, [rbp+0D0h+var_C0]
0x18001571d  mov     r8d, ebx; unsigned int
0x180015720  lea     r9, [rbp+0D0h+var_110]; unsigned int *
0x180015724  mov     [rsp+1D0h+var_1B0], rax; unsigned __int16 **
0x180015729  mov     rcx, rdi; this
0x18001572c  call    ?_Append@CBsString@@AEAAJKKQEAKQEAPEBG@Z; CBsString::_Append(ulong,ulong,ulong * const,ushort const * * const)
0x180015731  mov     rcx, [rbp+0D0h+var_20]
0x180015738  xor     rcx, rsp; StackCookie
0x18001573b  call    __security_check_cookie
0x180015740  lea     r11, [rsp+1D0h+var_10]
0x180015748  mov     rbx, [r11+28h]
0x18001574c  mov     rsi, [r11+30h]
0x180015750  mov     rsp, r11
0x180015753  pop     r14
0x180015755  pop     rdi
0x180015756  pop     rbp
0x180015757  retn
```
