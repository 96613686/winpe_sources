# sub_1800EDFE8

- ea: `0x1800edfe8`
- end: `0x1800ee109`
- name: `sub_1800EDFE8`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800ee4d0`

## callees

- `0x180099098`
- `0x1800edfe8`
- `0x1800eebc0`
- `0x18020ca70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ee0f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ee0f1`

## pseudocode

```c
void __fastcall sub_1800EDFE8(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 i; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 j; // rdi
  _BYTE *v8; // rdx
  __int64 v9; // r8
  _BYTE *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  bool v13; // zf

  *(_QWORD *)a1 = off_180211C10;
  sub_1800EEBC0();
  v2 = *(_QWORD *)(a1 + 80);
  if ( v2 )
  {
    j__o_free(v2);
    *(_QWORD *)(a1 + 80) = 0;
  }
  v3 = *(_QWORD *)(a1 + 88);
  if ( v3 )
  {
    j__o_free(v3);
    *(_QWORD *)(a1 + 88) = 0;
  }
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 48); i = (unsigned int)(i + 1) )
  {
    v5 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8 * i);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *(_QWORD *)(a1 + 40);
  if ( v6 )
  {
    j__o_free(v6);
    *(_QWORD *)(a1 + 40) = 0;
  }
  for ( j = 0; (unsigned int)j < *(_DWORD *)(a1 + 72); j = (unsigned int)(j + 1) )
  {
    v8 = *(_BYTE **)(*(_QWORD *)(a1 + 56) + 8 * j);
    v9 = *(unsigned int *)(*(_QWORD *)(a1 + 64) + 4 * j);
    v10 = v8;
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 64) + 4 * j) )
    {
      do
      {
        *v10++ = 0;
        --v9;
      }
      while ( v9 );
    }
    if ( v8 )
      j__o_free(v8);
  }
  v11 = *(_QWORD *)(a1 + 56);
  if ( v11 )
  {
    j__o_free(v11);
    *(_QWORD *)(a1 + 56) = 0;
  }
  v12 = *(_QWORD *)(a1 + 64);
  if ( v12 )
  {
    j__o_free(v12);
    *(_QWORD *)(a1 + 64) = 0;
  }
  v13 = *(_DWORD *)(a1 + 696) == 0;
  *(_QWORD *)(a1 + 8) = 0;
  if ( v13 )
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 656));
}

```

## disassembly

```asm
0x1800edfe8  mov     [rsp+arg_0], rbx
0x1800edfed  push    rdi
0x1800edfee  sub     rsp, 20h
0x1800edff2  lea     rax, off_180211C10
0x1800edff9  mov     rbx, rcx
0x1800edffc  mov     [rcx], rax
0x1800edfff  call    sub_1800EEBC0
0x1800ee004  mov     rcx, [rbx+50h]
0x1800ee008  test    rcx, rcx
0x1800ee00b  jz      short loc_1800EE01A
0x1800ee00d  call    j__o_free
0x1800ee012  mov     qword ptr [rbx+50h], 0
0x1800ee01a  mov     rcx, [rbx+58h]
0x1800ee01e  test    rcx, rcx
0x1800ee021  jz      short loc_1800EE030
0x1800ee023  call    j__o_free
0x1800ee028  mov     qword ptr [rbx+58h], 0
0x1800ee030  xor     edi, edi
0x1800ee032  cmp     [rbx+30h], edi
0x1800ee035  jbe     short loc_1800EE058
0x1800ee037  mov     rax, [rbx+28h]
0x1800ee03b  mov     rcx, [rax+rdi*8]
0x1800ee03f  test    rcx, rcx
0x1800ee042  jz      short loc_1800EE051
0x1800ee044  mov     rax, [rcx]
0x1800ee047  mov     rax, [rax+10h]
0x1800ee04b  call    cs:__guard_dispatch_icall_fptr
0x1800ee051  inc     edi
0x1800ee053  cmp     edi, [rbx+30h]
0x1800ee056  jb      short loc_1800EE037
0x1800ee058  mov     rcx, [rbx+28h]
0x1800ee05c  test    rcx, rcx
0x1800ee05f  jz      short loc_1800EE06E
0x1800ee061  call    j__o_free
0x1800ee066  mov     qword ptr [rbx+28h], 0
0x1800ee06e  xor     edi, edi
0x1800ee070  cmp     [rbx+48h], edi
0x1800ee073  jbe     short loc_1800EE0AD
0x1800ee075  mov     rax, [rbx+38h]
0x1800ee079  mov     rdx, [rax+rdi*8]
0x1800ee07d  mov     rax, [rbx+40h]
0x1800ee081  mov     r8d, [rax+rdi*4]
0x1800ee085  mov     rax, rdx
0x1800ee088  test    r8, r8
0x1800ee08b  jz      short loc_1800EE099
0x1800ee08d  mov     byte ptr [rax], 0
0x1800ee090  inc     rax
0x1800ee093  sub     r8, 1
0x1800ee097  jnz     short loc_1800EE08D
0x1800ee099  test    rdx, rdx
0x1800ee09c  jz      short loc_1800EE0A6
0x1800ee09e  mov     rcx, rdx
0x1800ee0a1  call    j__o_free
0x1800ee0a6  inc     edi
0x1800ee0a8  cmp     edi, [rbx+48h]
0x1800ee0ab  jb      short loc_1800EE075
0x1800ee0ad  mov     rcx, [rbx+38h]
0x1800ee0b1  test    rcx, rcx
0x1800ee0b4  jz      short loc_1800EE0C3
0x1800ee0b6  call    j__o_free
0x1800ee0bb  mov     qword ptr [rbx+38h], 0
0x1800ee0c3  mov     rcx, [rbx+40h]
0x1800ee0c7  test    rcx, rcx
0x1800ee0ca  jz      short loc_1800EE0D9
0x1800ee0cc  call    j__o_free
0x1800ee0d1  mov     qword ptr [rbx+40h], 0
0x1800ee0d9  cmp     dword ptr [rbx+2B8h], 0
0x1800ee0e0  mov     qword ptr [rbx+8], 0
0x1800ee0e8  jnz     short loc_1800EE0FD
0x1800ee0ea  lea     rcx, [rbx+290h]; lpCriticalSection
0x1800ee0f1  call    cs:DeleteCriticalSection
0x1800ee0f8  nop     dword ptr [rax+rax+00h]
0x1800ee0fd  mov     rbx, [rsp+28h+arg_0]
0x1800ee102  add     rsp, 20h
0x1800ee106  pop     rdi
0x1800ee107  retn
```
