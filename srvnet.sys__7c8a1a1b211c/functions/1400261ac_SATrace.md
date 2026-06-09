# SATrace

- ea: `0x1400261ac`
- end: `0x14002637b`
- name: `SATrace`
- size: `463`
- prototype: `NTSTATUS __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int64, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int, __int64, __int64, __int64, __int64, char)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140004bc0`
- `0x1400051f0`
- `0x140006070`
- `0x140006b20`
- `0x140023260`
- `0x140023370`

## callees

- `0x1400261ac`
- `0x14002a3e0`
- `0x14002a840`

## import_xrefs

- `ntoskrnl!IoWMIWriteEvent` at `0x140026354`
- `ntoskrnl!IoWMIWriteEvent` at `0x140026354`

## pseudocode

```c
NTSTATUS __fastcall SATrace(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        char a13)
{
  __int64 v16; // rcx
  _QWORD WnodeEventItem[22]; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v19[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v20; // [rsp+D8h] [rbp-28h]
  __int64 v21; // [rsp+E0h] [rbp-20h]
  __int64 v22; // [rsp+E8h] [rbp-18h]
  __int64 v23; // [rsp+F0h] [rbp-10h]
  __int128 v24; // [rsp+F8h] [rbp-8h]

  memset(WnodeEventItem, 0, sizeof(WnodeEventItem));
  LOWORD(WnodeEventItem[0]) = 176;
  WnodeEventItem[3] = SrvAdminEventingGuid;
  BYTE4(WnodeEventItem[0]) = a13;
  HIDWORD(WnodeEventItem[5]) = 1703936;
  HIWORD(WnodeEventItem[0]) = 1;
  WnodeEventItem[1] = 0;
  if ( a1 )
  {
    LODWORD(WnodeEventItem[9]) = *a1;
    WnodeEventItem[8] = *((_QWORD *)a1 + 1);
  }
  else
  {
    LODWORD(WnodeEventItem[9]) = 0;
    WnodeEventItem[8] = 0;
  }
  if ( a3 )
  {
    LODWORD(WnodeEventItem[11]) = *a3;
    WnodeEventItem[10] = *((_QWORD *)a3 + 1);
  }
  else
  {
    LODWORD(WnodeEventItem[11]) = 0;
    WnodeEventItem[10] = 0;
  }
  LODWORD(WnodeEventItem[13]) = 0;
  WnodeEventItem[12] = 0;
  if ( a5 )
  {
    LODWORD(WnodeEventItem[15]) = *a5;
    WnodeEventItem[14] = *((_QWORD *)a5 + 1);
  }
  else
  {
    LODWORD(WnodeEventItem[15]) = 0;
    WnodeEventItem[14] = 0;
  }
  if ( a6 )
  {
    LODWORD(WnodeEventItem[17]) = *a6;
    WnodeEventItem[16] = *((_QWORD *)a6 + 1);
  }
  else
  {
    LODWORD(WnodeEventItem[17]) = 0;
    WnodeEventItem[16] = 0;
  }
  if ( a7 )
  {
    LODWORD(WnodeEventItem[19]) = *a7;
    WnodeEventItem[18] = *((_QWORD *)a7 + 1);
  }
  else
  {
    LODWORD(WnodeEventItem[19]) = 0;
    WnodeEventItem[18] = 0;
  }
  if ( a2 )
  {
    LODWORD(WnodeEventItem[21]) = *a2;
    WnodeEventItem[20] = *((_QWORD *)a2 + 1);
  }
  else
  {
    LODWORD(WnodeEventItem[21]) = 0;
    WnodeEventItem[20] = 0;
  }
  v19[0] = a8;
  v16 = 0;
  v22 = a11;
  v21 = a10;
  v23 = a12;
  v20 = a9;
  v19[1] = 0;
  v24 = 0;
  do
  {
    *((_WORD *)&v24 + v16) = WnodeEventItem[2 * v16 + 7];
    ++v16;
  }
  while ( v16 != 8 );
  LODWORD(WnodeEventItem[7]) = 56;
  WnodeEventItem[6] = v19;
  return IoWMIWriteEvent(WnodeEventItem);
}

```

## disassembly

```asm
0x1400261ac  push    rbp
0x1400261ae  push    rbx
0x1400261af  push    rsi
0x1400261b0  push    rdi
0x1400261b1  push    r14
0x1400261b3  lea     rbp, [rsp-10h]
0x1400261b8  sub     rsp, 110h
0x1400261bf  mov     rax, cs:__security_cookie
0x1400261c6  xor     rax, rsp
0x1400261c9  mov     [rbp+30h+var_28], rax
0x1400261cd  mov     rbx, r8
0x1400261d0  mov     rdi, rdx
0x1400261d3  mov     rsi, rcx
0x1400261d6  mov     r14d, 0B0h
0x1400261dc  mov     r8d, r14d; Size
0x1400261df  lea     rcx, [rsp+130h+WnodeEventItem]; void *
0x1400261e4  xor     edx, edx; Val
0x1400261e6  call    memset
0x1400261eb  lea     rax, SrvAdminEventingGuid
0x1400261f2  mov     [rsp+130h+WnodeEventItem], r14w
0x1400261f8  xor     edx, edx
0x1400261fa  mov     [rsp+130h+var_F8], rax
0x1400261ff  mov     al, [rbp+30h+arg_60]
0x140026205  mov     r8d, 1
0x14002620b  mov     [rsp+130h+var_10C], al
0x14002620f  mov     [rsp+130h+var_E4], 1A0000h
0x140026217  mov     [rsp+130h+var_10A], r8w
0x14002621d  mov     [rsp+130h+var_108], rdx
0x140026222  test    rsi, rsi
0x140026225  jnz     short loc_140026232
0x140026227  mov     [rsp+130h+var_C8], edx
0x14002622b  mov     [rsp+130h+var_D0], rdx
0x140026230  jmp     short loc_140026242
0x140026232  movzx   eax, word ptr [rsi]
0x140026235  mov     [rsp+130h+var_C8], eax
0x140026239  mov     rax, [rsi+8]
0x14002623d  mov     [rsp+130h+var_D0], rax
0x140026242  test    rbx, rbx
0x140026245  jnz     short loc_140026252
0x140026247  mov     [rsp+130h+var_B8], edx
0x14002624b  mov     [rsp+130h+var_C0], rdx
0x140026250  jmp     short loc_140026262
0x140026252  movzx   eax, word ptr [rbx]
0x140026255  mov     [rsp+130h+var_B8], eax
0x140026259  mov     rax, [rbx+8]
0x14002625d  mov     [rsp+130h+var_C0], rax
0x140026262  mov     rcx, [rbp+30h+arg_20]
0x140026266  mov     [rbp+30h+var_A8], edx
0x140026269  mov     [rbp+30h+var_B0], rdx
0x14002626d  test    rcx, rcx
0x140026270  jnz     short loc_14002627B
0x140026272  mov     [rbp+30h+var_98], edx
0x140026275  mov     [rbp+30h+var_A0], rdx
0x140026279  jmp     short loc_140026289
0x14002627b  movzx   eax, word ptr [rcx]
0x14002627e  mov     [rbp+30h+var_98], eax
0x140026281  mov     rax, [rcx+8]
0x140026285  mov     [rbp+30h+var_A0], rax
0x140026289  mov     rcx, [rbp+30h+arg_28]
0x14002628d  test    rcx, rcx
0x140026290  jnz     short loc_14002629B
0x140026292  mov     [rbp+30h+var_88], edx
0x140026295  mov     [rbp+30h+var_90], rdx
0x140026299  jmp     short loc_1400262A9
0x14002629b  movzx   eax, word ptr [rcx]
0x14002629e  mov     [rbp+30h+var_88], eax
0x1400262a1  mov     rax, [rcx+8]
0x1400262a5  mov     [rbp+30h+var_90], rax
0x1400262a9  mov     rcx, [rbp+30h+arg_30]
0x1400262ad  test    rcx, rcx
0x1400262b0  jnz     short loc_1400262BB
0x1400262b2  mov     [rbp+30h+var_78], edx
0x1400262b5  mov     [rbp+30h+var_80], rdx
0x1400262b9  jmp     short loc_1400262C9
0x1400262bb  movzx   eax, word ptr [rcx]
0x1400262be  mov     [rbp+30h+var_78], eax
0x1400262c1  mov     rax, [rcx+8]
0x1400262c5  mov     [rbp+30h+var_80], rax
0x1400262c9  test    rdi, rdi
0x1400262cc  jnz     short loc_1400262D7
0x1400262ce  mov     [rbp+30h+var_68], edx
0x1400262d1  mov     [rbp+30h+var_70], rdx
0x1400262d5  jmp     short loc_1400262E5
0x1400262d7  movzx   eax, word ptr [rdi]
0x1400262da  mov     [rbp+30h+var_68], eax
0x1400262dd  mov     rax, [rdi+8]
0x1400262e1  mov     [rbp+30h+var_70], rax
0x1400262e5  mov     eax, [rbp+30h+arg_38]
0x1400262e8  xorps   xmm0, xmm0
0x1400262eb  mov     [rbp+30h+var_60], eax
0x1400262ee  mov     rcx, rdx
0x1400262f1  mov     rax, [rbp+30h+arg_50]
0x1400262f8  mov     [rbp+30h+var_48], rax
0x1400262fc  mov     rax, [rbp+30h+arg_48]
0x140026303  mov     [rbp+30h+var_50], rax
0x140026307  mov     rax, [rbp+30h+arg_58]
0x14002630e  mov     [rbp+30h+var_40], rax
0x140026312  mov     rax, [rbp+30h+arg_40]
0x140026319  mov     [rbp+30h+var_58], rax
0x14002631d  mov     [rbp+30h+var_5C], edx
0x140026320  movdqu  [rbp+30h+var_38], xmm0
0x140026325  mov     rax, rcx
0x140026328  add     rax, rax
0x14002632b  movzx   eax, word ptr [rsp+rax*8+130h+var_D8]
0x140026330  mov     word ptr [rbp+rcx*2+30h+var_38], ax
0x140026335  add     rcx, r8
0x140026338  cmp     rcx, 8
0x14002633c  jnz     short loc_140026325
0x14002633e  lea     rax, [rbp+30h+var_60]
0x140026342  mov     [rsp+130h+var_D8], 38h ; '8'
0x14002634a  lea     rcx, [rsp+130h+WnodeEventItem]; WnodeEventItem
0x14002634f  mov     [rsp+130h+var_E0], rax
0x140026354  call    cs:__imp_IoWMIWriteEvent
0x14002635b  nop     dword ptr [rax+rax+00h]
0x140026360  mov     rcx, [rbp+30h+var_28]
0x140026364  xor     rcx, rsp; StackCookie
0x140026367  call    __security_check_cookie
0x14002636c  add     rsp, 110h
0x140026373  pop     r14
0x140026375  pop     rdi
0x140026376  pop     rsi
0x140026377  pop     rbx
0x140026378  pop     rbp
0x140026379  retn
```
