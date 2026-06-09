# FWUPDATE_ParseUsb4DromForVidPid

- ea: `0x140041570`
- end: `0x1400416cd`
- name: `FWUPDATE_ParseUsb4DromForVidPid`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140008640`

## callees

- `0x1400067ac`
- `0x14002d940`
- `0x140041570`

## pseudocode

```c
void __fastcall FWUPDATE_ParseUsb4DromForVidPid(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // r9
  unsigned __int8 *v4; // rbx
  unsigned __int8 *v5; // rdx
  char v6; // al
  int v7; // r9d
  int v8; // edx

  v2 = *(_QWORD *)(a1 + 2704);
  if ( *(_BYTE *)(v2 + 13) != 1 )
    return;
  v3 = *(unsigned int *)(a1 + 2700);
  v4 = (unsigned __int8 *)(v2 + 22);
  while ( 1 )
  {
    v5 = (unsigned __int8 *)*v4;
    if ( !(_BYTE)v5 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return;
      v7 = 44;
      goto LABEL_17;
    }
    v5 = &v5[(_QWORD)v4];
    if ( (unsigned __int64)v5 > v2 + v3 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return;
      v7 = 45;
      goto LABEL_17;
    }
    v6 = v4[1];
    if ( v6 >= 0 && (v6 & 0x3F) == 9 )
      break;
    v4 = v5;
    if ( (unsigned __int64)v5 >= v2 + v3 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return;
      v7 = 47;
LABEL_17:
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(a1 + 2536),
        (_DWORD)v5,
        3,
        v7,
        (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids);
      return;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v8 = *((unsigned __int16 *)v4 + 3);
    LOBYTE(v8) = 4;
    WPP_RECORDER_SF_DDDD(
      *(_QWORD *)(a1 + 2536),
      v8,
      3,
      46,
      (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids,
      *((_WORD *)v4 + 2),
      *((_WORD *)v4 + 3),
      *((_WORD *)v4 + 4),
      v4[14]);
  }
  *(_WORD *)(a1 + 2736) = *((_WORD *)v4 + 2);
  *(_WORD *)(a1 + 2738) = *((_WORD *)v4 + 3);
  *(_WORD *)(a1 + 2740) = *((_WORD *)v4 + 4);
  *(_WORD *)(a1 + 2742) = v4[14];
  *(_BYTE *)(a1 + 2744) = 1;
}

```

## disassembly

```asm
0x140041570  mov     [rsp+arg_0], rbx
0x140041575  push    rdi
0x140041576  sub     rsp, 50h
0x14004157a  mov     rdi, rcx
0x14004157d  mov     rcx, [rcx+0A90h]
0x140041584  cmp     byte ptr [rcx+0Dh], 1
0x140041588  jnz     loc_1400416C1
0x14004158e  mov     r9d, [rdi+0A8Ch]
0x140041595  lea     rbx, [rcx+16h]
0x140041599  movzx   edx, byte ptr [rbx]
0x14004159c  test    dl, dl
0x14004159e  jz      loc_14004168B
0x1400415a4  lea     r8, [rcx+r9]
0x1400415a8  add     rdx, rbx
0x1400415ab  cmp     rdx, r8
0x1400415ae  ja      loc_140041673
0x1400415b4  mov     al, [rbx+1]
0x1400415b7  test    al, al
0x1400415b9  js      short loc_1400415C1
0x1400415bb  and     al, 3Fh
0x1400415bd  cmp     al, 9
0x1400415bf  jz      short loc_1400415E8
0x1400415c1  mov     rbx, rdx
0x1400415c4  cmp     rdx, r8
0x1400415c7  jb      short loc_140041599
0x1400415c9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400415d0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400415d7  jz      loc_1400416C1
0x1400415dd  mov     r9d, 2Fh ; '/'
0x1400415e3  jmp     loc_1400416A1
0x1400415e8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400415ef  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400415f6  jz      short loc_14004163E
0x1400415f8  movzx   eax, byte ptr [rbx+0Eh]
0x1400415fc  mov     r9d, 2Eh ; '.'
0x140041602  movzx   ecx, word ptr [rbx+8]
0x140041606  movzx   edx, word ptr [rbx+6]
0x14004160a  movzx   r8d, word ptr [rbx+4]
0x14004160f  mov     [rsp+58h+var_18], eax
0x140041613  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x14004161a  mov     [rsp+58h+var_20], ecx
0x14004161e  mov     rcx, [rdi+9E8h]
0x140041625  mov     [rsp+58h+var_28], edx
0x140041629  mov     dl, 4
0x14004162b  mov     [rsp+58h+var_30], r8d
0x140041630  lea     r8d, [r9-2Bh]
0x140041634  mov     [rsp+58h+var_38], rax
0x140041639  call    WPP_RECORDER_SF_DDDD
0x14004163e  movzx   eax, word ptr [rbx+4]
0x140041642  mov     [rdi+0AB0h], ax
0x140041649  movzx   eax, word ptr [rbx+6]
0x14004164d  mov     [rdi+0AB2h], ax
0x140041654  movzx   eax, word ptr [rbx+8]
0x140041658  mov     [rdi+0AB4h], ax
0x14004165f  movzx   eax, byte ptr [rbx+0Eh]
0x140041663  mov     [rdi+0AB6h], ax
0x14004166a  mov     byte ptr [rdi+0AB8h], 1
0x140041671  jmp     short loc_1400416C1
0x140041673  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004167a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140041681  jz      short loc_1400416C1
0x140041683  mov     r9d, 2Dh ; '-'
0x140041689  jmp     short loc_1400416A1
0x14004168b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140041692  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140041699  jz      short loc_1400416C1
0x14004169b  mov     r9d, 2Ch ; ','
0x1400416a1  mov     rcx, [rdi+9E8h]
0x1400416a8  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x1400416af  mov     r8d, 3
0x1400416b5  mov     [rsp+58h+var_38], rax
0x1400416ba  mov     dl, 2
0x1400416bc  call    WPP_RECORDER_SF_
0x1400416c1  mov     rbx, [rsp+58h+arg_0]
0x1400416c6  add     rsp, 50h
0x1400416ca  pop     rdi
0x1400416cb  retn
```
