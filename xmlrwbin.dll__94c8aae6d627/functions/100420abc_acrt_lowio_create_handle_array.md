# __acrt_lowio_create_handle_array

- ea: `0x100420abc`
- end: `0x100420b61`
- name: `__acrt_lowio_create_handle_array`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x100420bc0`

## callees

- `0x10041c1d0`
- `0x10041c24c`
- `0x10041e1f8`
- `0x100420abc`

## pseudocode

```c
char *_acrt_lowio_create_handle_array()
{
  char *v0; // rax
  char *v1; // rsi
  char *v2; // rbx
  char *v3; // rbp
  char *v4; // rdi
  _BYTE *v5; // rcx
  unsigned int v6; // eax

  v0 = (char *)calloc_base(0x40u, 0x48u);
  v1 = 0;
  v2 = v0;
  if ( v0 )
  {
    v3 = v0 + 4608;
    v4 = v0 + 48;
    do
    {
      _acrt_InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v4 - 48), 0xFA0u);
      *((_QWORD *)v4 - 1) = -1;
      v5 = v4 + 14;
      v4[13] &= 0xF8u;
      v6 = 0;
      *(_QWORD *)v4 = 0;
      *((_DWORD *)v4 + 2) = 168427520;
      v4[12] = 10;
      do
      {
        *v5 = 0;
        ++v6;
        ++v5;
      }
      while ( v6 < 5 );
      v4 += 72;
    }
    while ( v4 - 48 != v3 );
    v1 = v2;
  }
  free_base(0);
  return v1;
}

```

## disassembly

```asm
0x100420abc  mov     [rsp+arg_0], rbx
0x100420ac1  mov     [rsp+arg_8], rbp
0x100420ac6  mov     [rsp+arg_10], rsi
0x100420acb  push    rdi
0x100420acc  sub     rsp, 20h
0x100420ad0  mov     edx, 48h ; 'H'; Size
0x100420ad5  lea     ecx, [rdx-8]; Count
0x100420ad8  call    _calloc_base
0x100420add  xor     esi, esi
0x100420adf  mov     rbx, rax
0x100420ae2  test    rax, rax
0x100420ae5  jz      short loc_100420B42
0x100420ae7  lea     rbp, [rax+1200h]
0x100420aee  cmp     rax, rbp
0x100420af1  jz      short loc_100420B3F
0x100420af3  lea     rdi, [rax+30h]
0x100420af7  lea     rcx, [rdi-30h]; lpCriticalSection
0x100420afb  xor     r8d, r8d
0x100420afe  mov     edx, 0FA0h; dwSpinCount
0x100420b03  call    __acrt_InitializeCriticalSectionEx
0x100420b08  or      qword ptr [rdi-8], 0FFFFFFFFFFFFFFFFh
0x100420b0d  lea     rcx, [rdi+0Eh]
0x100420b11  and     byte ptr [rdi+0Dh], 0F8h
0x100420b15  mov     eax, esi
0x100420b17  mov     [rdi], rsi
0x100420b1a  mov     dword ptr [rdi+8], 0A0A0000h
0x100420b21  mov     byte ptr [rdi+0Ch], 0Ah
0x100420b25  mov     [rcx], sil
0x100420b28  inc     eax
0x100420b2a  inc     rcx
0x100420b2d  cmp     eax, 5
0x100420b30  jb      short loc_100420B25
0x100420b32  add     rdi, 48h ; 'H'
0x100420b36  lea     rax, [rdi-30h]
0x100420b3a  cmp     rax, rbp
0x100420b3d  jnz     short loc_100420AF7
0x100420b3f  mov     rsi, rbx
0x100420b42  xor     ecx, ecx; Block
0x100420b44  call    _free_base
0x100420b49  mov     rbx, [rsp+28h+arg_0]
0x100420b4e  mov     rax, rsi
0x100420b51  mov     rsi, [rsp+28h+arg_10]
0x100420b56  mov     rbp, [rsp+28h+arg_8]
0x100420b5b  add     rsp, 20h
0x100420b5f  pop     rdi
0x100420b60  retn
```
