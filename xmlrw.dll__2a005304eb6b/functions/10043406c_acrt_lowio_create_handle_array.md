# __acrt_lowio_create_handle_array

- ea: `0x10043406c`
- end: `0x100434111`
- name: `__acrt_lowio_create_handle_array`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x100434170`

## callees

- `0x10042e760`
- `0x10042e7dc`
- `0x100430788`
- `0x10043406c`

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
0x10043406c  mov     [rsp+arg_0], rbx
0x100434071  mov     [rsp+arg_8], rbp
0x100434076  mov     [rsp+arg_10], rsi
0x10043407b  push    rdi
0x10043407c  sub     rsp, 20h
0x100434080  mov     edx, 48h ; 'H'; Size
0x100434085  lea     ecx, [rdx-8]; Count
0x100434088  call    _calloc_base
0x10043408d  xor     esi, esi
0x10043408f  mov     rbx, rax
0x100434092  test    rax, rax
0x100434095  jz      short loc_1004340F2
0x100434097  lea     rbp, [rax+1200h]
0x10043409e  cmp     rax, rbp
0x1004340a1  jz      short loc_1004340EF
0x1004340a3  lea     rdi, [rax+30h]
0x1004340a7  lea     rcx, [rdi-30h]; lpCriticalSection
0x1004340ab  xor     r8d, r8d
0x1004340ae  mov     edx, 0FA0h; dwSpinCount
0x1004340b3  call    __acrt_InitializeCriticalSectionEx
0x1004340b8  or      qword ptr [rdi-8], 0FFFFFFFFFFFFFFFFh
0x1004340bd  lea     rcx, [rdi+0Eh]
0x1004340c1  and     byte ptr [rdi+0Dh], 0F8h
0x1004340c5  mov     eax, esi
0x1004340c7  mov     [rdi], rsi
0x1004340ca  mov     dword ptr [rdi+8], 0A0A0000h
0x1004340d1  mov     byte ptr [rdi+0Ch], 0Ah
0x1004340d5  mov     [rcx], sil
0x1004340d8  inc     eax
0x1004340da  inc     rcx
0x1004340dd  cmp     eax, 5
0x1004340e0  jb      short loc_1004340D5
0x1004340e2  add     rdi, 48h ; 'H'
0x1004340e6  lea     rax, [rdi-30h]
0x1004340ea  cmp     rax, rbp
0x1004340ed  jnz     short loc_1004340A7
0x1004340ef  mov     rsi, rbx
0x1004340f2  xor     ecx, ecx; Block
0x1004340f4  call    _free_base
0x1004340f9  mov     rbx, [rsp+28h+arg_0]
0x1004340fe  mov     rax, rsi
0x100434101  mov     rsi, [rsp+28h+arg_10]
0x100434106  mov     rbp, [rsp+28h+arg_8]
0x10043410b  add     rsp, 20h
0x10043410f  pop     rdi
0x100434110  retn
```
