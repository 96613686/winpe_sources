# UpdatePageFaultCount

- ea: `0x14000a468`
- end: `0x14000a597`
- name: `UpdatePageFaultCount`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400078ec`

## callees

- `0x14000a468`

## pseudocode

```c
void __fastcall UpdatePageFaultCount(_DWORD *a1, __int64 a2, unsigned __int64 a3, unsigned __int8 a4)
{
  unsigned __int64 v4; // r10
  int v5; // r11d
  bool v6; // r9
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax

  v4 = *(_QWORD *)(a2 + 24);
  v5 = a4;
  v6 = a3 >= v4 && a3 < *(_QWORD *)(a2 + 32) + v4;
  switch ( v5 )
  {
    case 10:
      if ( v6 )
      {
        ++a1[50];
        ++*(_DWORD *)(a2 + 60);
        v13 = *(_QWORD *)(a2 + 80);
        if ( v13 )
          ++*(_DWORD *)(v13 + 60);
      }
      else
      {
        ++a1[46];
        ++*(_DWORD *)(a2 + 44);
        v14 = *(_QWORD *)(a2 + 80);
        if ( v14 )
          ++*(_DWORD *)(v14 + 44);
      }
      break;
    case 11:
      if ( v6 )
      {
        ++a1[51];
        ++*(_DWORD *)(a2 + 64);
        v11 = *(_QWORD *)(a2 + 80);
        if ( v11 )
          ++*(_DWORD *)(v11 + 64);
      }
      else
      {
        ++a1[47];
        ++*(_DWORD *)(a2 + 48);
        v12 = *(_QWORD *)(a2 + 80);
        if ( v12 )
          ++*(_DWORD *)(v12 + 48);
      }
      break;
    case 12:
      if ( v6 )
      {
        ++a1[52];
        ++*(_DWORD *)(a2 + 68);
        v9 = *(_QWORD *)(a2 + 80);
        if ( v9 )
          ++*(_DWORD *)(v9 + 68);
      }
      else
      {
        ++a1[48];
        ++*(_DWORD *)(a2 + 52);
        v10 = *(_QWORD *)(a2 + 80);
        if ( v10 )
          ++*(_DWORD *)(v10 + 52);
      }
      break;
    case 14:
      if ( v6 )
      {
        ++a1[49];
        ++*(_DWORD *)(a2 + 56);
        v7 = *(_QWORD *)(a2 + 80);
        if ( v7 )
          ++*(_DWORD *)(v7 + 56);
      }
      else
      {
        ++a1[45];
        ++*(_DWORD *)(a2 + 40);
        v8 = *(_QWORD *)(a2 + 80);
        if ( v8 )
          ++*(_DWORD *)(v8 + 40);
      }
      break;
  }
}

```

## disassembly

```asm
0x14000a468  mov     [rsp+arg_0], rbx
0x14000a46d  mov     r10, [rdx+18h]
0x14000a471  mov     ebx, 1
0x14000a476  movzx   r11d, r9b
0x14000a47a  cmp     r8, r10
0x14000a47d  jb      short loc_14000A48D
0x14000a47f  add     r10, [rdx+20h]
0x14000a483  cmp     r8, r10
0x14000a486  jnb     short loc_14000A48D
0x14000a488  mov     r9b, bl
0x14000a48b  jmp     short loc_14000A490
0x14000a48d  xor     r9b, r9b
0x14000a490  mov     r8d, r11d
0x14000a493  sub     r8d, 0Ah
0x14000a497  jz      loc_14000A560
0x14000a49d  sub     r8d, ebx
0x14000a4a0  jz      loc_14000A52D
0x14000a4a6  sub     r8d, ebx
0x14000a4a9  jz      short loc_14000A4F6
0x14000a4ab  cmp     r8d, 2
0x14000a4af  jnz     loc_14000A591
0x14000a4b5  test    r9b, r9b
0x14000a4b8  jz      short loc_14000A4D8
0x14000a4ba  add     [rcx+0C4h], ebx
0x14000a4c0  add     [rdx+38h], ebx
0x14000a4c3  mov     rax, [rdx+50h]
0x14000a4c7  test    rax, rax
0x14000a4ca  jz      loc_14000A591
0x14000a4d0  add     [rax+38h], ebx
0x14000a4d3  jmp     loc_14000A591
0x14000a4d8  add     [rcx+0B4h], ebx
0x14000a4de  add     [rdx+28h], ebx
0x14000a4e1  mov     rax, [rdx+50h]
0x14000a4e5  test    rax, rax
0x14000a4e8  jz      loc_14000A591
0x14000a4ee  add     [rax+28h], ebx
0x14000a4f1  jmp     loc_14000A591
0x14000a4f6  test    r9b, r9b
0x14000a4f9  jz      short loc_14000A516
0x14000a4fb  add     [rcx+0D0h], ebx
0x14000a501  add     [rdx+44h], ebx
0x14000a504  mov     rax, [rdx+50h]
0x14000a508  test    rax, rax
0x14000a50b  jz      loc_14000A591
0x14000a511  add     [rax+44h], ebx
0x14000a514  jmp     short loc_14000A591
0x14000a516  add     [rcx+0C0h], ebx
0x14000a51c  add     [rdx+34h], ebx
0x14000a51f  mov     rax, [rdx+50h]
0x14000a523  test    rax, rax
0x14000a526  jz      short loc_14000A591
0x14000a528  add     [rax+34h], ebx
0x14000a52b  jmp     short loc_14000A591
0x14000a52d  test    r9b, r9b
0x14000a530  jz      short loc_14000A549
0x14000a532  add     [rcx+0CCh], ebx
0x14000a538  add     [rdx+40h], ebx
0x14000a53b  mov     rax, [rdx+50h]
0x14000a53f  test    rax, rax
0x14000a542  jz      short loc_14000A591
0x14000a544  add     [rax+40h], ebx
0x14000a547  jmp     short loc_14000A591
0x14000a549  add     [rcx+0BCh], ebx
0x14000a54f  add     [rdx+30h], ebx
0x14000a552  mov     rax, [rdx+50h]
0x14000a556  test    rax, rax
0x14000a559  jz      short loc_14000A591
0x14000a55b  add     [rax+30h], ebx
0x14000a55e  jmp     short loc_14000A591
0x14000a560  test    r9b, r9b
0x14000a563  jz      short loc_14000A57C
0x14000a565  add     [rcx+0C8h], ebx
0x14000a56b  add     [rdx+3Ch], ebx
0x14000a56e  mov     rax, [rdx+50h]
0x14000a572  test    rax, rax
0x14000a575  jz      short loc_14000A591
0x14000a577  add     [rax+3Ch], ebx
0x14000a57a  jmp     short loc_14000A591
0x14000a57c  add     [rcx+0B8h], ebx
0x14000a582  add     [rdx+2Ch], ebx
0x14000a585  mov     rax, [rdx+50h]
0x14000a589  test    rax, rax
0x14000a58c  jz      short loc_14000A591
0x14000a58e  add     [rax+2Ch], ebx
0x14000a591  mov     rbx, [rsp+arg_0]
0x14000a596  retn
```
