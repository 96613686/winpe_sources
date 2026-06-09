# HrRegQueryDword(HKEY__ *,ushort const *,ulong *)

- ea: `0x18000b4c8`
- end: `0x18000b57c`
- name: `?HrRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z`
- size: `180`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800096b0`
- `0x180009c80`

## callees

- `0x180003728`
- `0x180009bcc`
- `0x18000b4c8`
- `0x18000b584`

## pseudocode

```c
__int64 __fastcall HrRegQueryDword(HKEY a1, const unsigned __int16 *a2, unsigned __int8 *a3)
{
  unsigned int v5; // ebx
  unsigned int v7[14]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v8; // [rsp+88h] [rbp+20h] BYREF

  v8 = 0;
  v7[0] = 4;
  v5 = HrRegQueryValueEx(a1, a2, &v8, a3, v7);
  if ( !v5 )
  {
    if ( v8 == 4 )
      return v5;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9d0e4534345d32ff9b9263fa711fe616_Traceguids, a2);
    v5 = -2147023092;
  }
  *(_DWORD *)a3 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_9d0e4534345d32ff9b9263fa711fe616_Traceguids,
      (_DWORD)a2,
      v5);
  return v5;
}

```

## disassembly

```asm
0x18000b4c8  mov     r11, rsp
0x18000b4cb  push    rbx
0x18000b4cc  push    rbp
0x18000b4cd  push    rsi
0x18000b4ce  push    rdi
0x18000b4cf  sub     rsp, 48h
0x18000b4d3  mov     rdi, r8
0x18000b4d6  mov     dword ptr [r11+20h], 0
0x18000b4de  lea     rax, [r11-38h]
0x18000b4e2  mov     [rsp+68h+var_38], 4
0x18000b4ea  mov     r9, r8; unsigned __int8 *
0x18000b4ed  mov     [r11-48h], rax
0x18000b4f1  lea     r8, [r11+20h]; unsigned int *
0x18000b4f5  mov     rsi, rdx
0x18000b4f8  call    ?HrRegQueryValueEx@@YAJPEAUHKEY__@@PEBGPEAKPEAE2@Z; HrRegQueryValueEx(HKEY__ *,ushort const *,ulong *,uchar *,ulong *)
0x18000b4fd  lea     rbp, WPP_GLOBAL_Control
0x18000b504  mov     ebx, eax
0x18000b506  test    eax, eax
0x18000b508  jnz     short loc_18000B541
0x18000b50a  cmp     [rsp+68h+arg_18], 4
0x18000b512  jz      short loc_18000B571
0x18000b514  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b51b  cmp     rcx, rbp
0x18000b51e  jz      short loc_18000B53C
0x18000b520  test    byte ptr [rcx+1Ch], 1
0x18000b524  jz      short loc_18000B53C
0x18000b526  mov     rcx, [rcx+10h]
0x18000b52a  lea     edx, [rax+0Ah]
0x18000b52d  mov     r9, rsi
0x18000b530  lea     r8, WPP_9d0e4534345d32ff9b9263fa711fe616_Traceguids
0x18000b537  call    WPP_SF_S
0x18000b53c  mov     ebx, 8007070Ch
0x18000b541  xor     eax, eax
0x18000b543  mov     [rdi], eax
0x18000b545  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b54c  cmp     rcx, rbp
0x18000b54f  jz      short loc_18000B571
0x18000b551  test    byte ptr [rcx+1Ch], 1
0x18000b555  jz      short loc_18000B571
0x18000b557  mov     rcx, [rcx+10h]
0x18000b55b  lea     edx, [rax+0Bh]
0x18000b55e  mov     r9, rsi
0x18000b561  mov     [rsp+68h+var_48], ebx
0x18000b565  lea     r8, WPP_9d0e4534345d32ff9b9263fa711fe616_Traceguids
0x18000b56c  call    WPP_SF_Sd
0x18000b571  mov     eax, ebx
0x18000b573  add     rsp, 48h
0x18000b577  pop     rdi
0x18000b578  pop     rsi
0x18000b579  pop     rbp
0x18000b57a  pop     rbx
0x18000b57b  retn
```
