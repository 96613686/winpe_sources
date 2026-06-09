# NtCreateEvent

- ea: `0x14009760c`
- end: `0x1400977fc`
- name: `NtCreateEvent`
- size: `496`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x140002ef0`
- `0x14009760c`
- `0x1400a0c00`
- `0x1400a0df8`
- `0x1400a18a0`
- `0x1400eff90`
- `0x1400f0120`
- `0x1400fc664`
- `0x1400fc7c0`

## pseudocode

```c
__int64 __fastcall NtCreateEvent(_QWORD *a1, unsigned int a2, __int64 a3, unsigned int a4, char a5)
{
  char v9; // si
  __int64 ULong64FromUser; // rdi
  int Event; // ebx
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v15; // [rsp+38h] [rbp-50h] BYREF
  __int64 v16; // [rsp+40h] [rbp-48h]
  __int64 v17; // [rsp+48h] [rbp-40h] BYREF
  __int64 v18; // [rsp+50h] [rbp-38h]

  v15 = 0;
  v17 = 0;
  v9 = *((_BYTE *)KeGetPcr()->NtTib.StackBase + 96);
  ULong64FromUser = 0;
  v18 = 0;
  if ( a4 < 2 )
  {
    if ( a3 && v9 == 1 )
    {
      ULong64FromUser = RtlReadULong64FromUser((volatile void *)(a3 + 16));
      v18 = ULong64FromUser;
    }
    Event = NkCreateEvent(a1, a2, a3, a4, a5);
  }
  else
  {
    Event = -1073741811;
  }
  if ( Event >= 0 && !ULong64FromUser )
  {
    v16 = 0;
    if ( v9 == 1 )
    {
      v12 = RtlReadULong64FromUser(a1);
      v16 = v12;
      Event = SkobCreateObjectEx(0, (__int64)&SkeShadowSyncObjectType, 0, &v17);
      if ( Event >= 0 )
      {
        v13 = v17;
        *(_BYTE *)(v17 + 4) = 0;
        if ( a4 )
        {
          *(_DWORD *)v13 = 0;
          *(_QWORD *)(v13 + 8) = 0;
          if ( a5 )
            *(_DWORD *)(v13 + 8) = 1;
        }
        else
        {
          *(_DWORD *)v13 = 1;
          *(_QWORD *)(v13 + 8) = a5 != 0;
        }
        Event = SkobCreateHandle(v13, 0, v12, (__int64)&v15);
        if ( Event >= 0 )
          RtlWriteULong64ToUser(a1, v15);
        SkobDereferenceObject(v13);
      }
      if ( Event < 0 && v12 )
        NkClose(v12);
    }
  }
  return (unsigned int)Event;
}

```

## disassembly

```asm
0x14009760c  mov     r11, rsp
0x14009760f  mov     [r11+10h], rbx
0x140097613  mov     [r11+20h], r9d
0x140097617  mov     [r11+8], rcx
0x14009761b  push    rsi
0x14009761c  push    rdi
0x14009761d  push    r12
0x14009761f  push    r14
0x140097621  push    r15
0x140097623  sub     rsp, 60h
0x140097627  mov     r14d, r9d
0x14009762a  mov     rbx, r8
0x14009762d  mov     r12d, edx
0x140097630  mov     r15, rcx
0x140097633  mov     qword ptr [r11-50h], 0
0x14009763b  mov     qword ptr [r11-40h], 0
0x140097643  mov     rax, gs:8
0x14009764c  mov     sil, [rax+60h]
0x140097650  mov     [rsp+88h+var_58], sil
0x140097655  xor     edi, edi
0x140097657  mov     [r11-38h], rdi
0x14009765b  test    r9d, r9d
0x14009765e  jz      short loc_14009766D
0x140097660  cmp     r9d, 1
0x140097664  jz      short loc_14009766D
0x140097666  mov     ebx, 0C000000Dh
0x14009766b  jmp     short loc_1400976C7
0x14009766d  test    rbx, rbx
0x140097670  jz      short loc_1400976A9
0x140097672  cmp     sil, 1
0x140097676  jnz     short loc_1400976A9
0x140097678  lea     rcx, [r8+10h]
0x14009767c  call    RtlReadULong64FromUser
0x140097681  mov     rdi, rax
0x140097684  mov     [rsp+88h+var_38], rax
0x140097689  jmp     short loc_1400976A9
0x14009768b  mov     ebx, eax
0x14009768d  mov     r14d, [rsp+88h+arg_18]
0x140097695  mov     r15, [rsp+88h+arg_0]
0x14009769d  mov     rdi, [rsp+88h+var_38]
0x1400976a2  mov     sil, [rsp+88h+var_58]
0x1400976a7  jmp     short loc_1400976C7
0x1400976a9  mov     al, [rsp+88h+arg_20]
0x1400976b0  mov     byte ptr [rsp+88h+var_68], al
0x1400976b4  mov     r9d, r14d
0x1400976b7  mov     r8, rbx
0x1400976ba  mov     edx, r12d
0x1400976bd  mov     rcx, r15
0x1400976c0  call    NkCreateEvent
0x1400976c5  mov     ebx, eax
0x1400976c7  test    ebx, ebx
0x1400976c9  js      loc_1400977E4
0x1400976cf  test    rdi, rdi
0x1400976d2  jnz     loc_1400977E4
0x1400976d8  mov     [rsp+88h+var_48], rdi
0x1400976dd  cmp     sil, 1
0x1400976e1  jnz     loc_1400977E4
0x1400976e7  mov     rcx, r15
0x1400976ea  call    RtlReadULong64FromUser
0x1400976ef  mov     rsi, rax
0x1400976f2  mov     [rsp+88h+var_48], rax
0x1400976f7  jmp     short loc_140097710
0x1400976f9  mov     ebx, eax
0x1400976fb  mov     r14d, [rsp+88h+arg_18]
0x140097703  mov     r15, [rsp+88h+arg_0]
0x14009770b  mov     rsi, [rsp+88h+var_48]
0x140097710  test    ebx, ebx
0x140097712  js      loc_1400977D7
0x140097718  lea     r9, [rsp+88h+var_40]
0x14009771d  xor     r8d, r8d
0x140097720  lea     rdx, SkeShadowSyncObjectType
0x140097727  xor     ecx, ecx
0x140097729  call    SkobCreateObjectEx
0x14009772e  mov     ebx, eax
0x140097730  test    eax, eax
0x140097732  js      loc_1400977D3
0x140097738  mov     rdi, [rsp+88h+var_40]
0x14009773d  mov     byte ptr [rdi+4], 0
0x140097741  test    r14d, r14d
0x140097744  jnz     short loc_14009775E
0x140097746  mov     dword ptr [rdi], 1
0x14009774c  xor     eax, eax
0x14009774e  cmp     [rsp+88h+arg_20], al
0x140097755  setnz   al
0x140097758  mov     [rdi+8], rax
0x14009775c  jmp     short loc_14009777D
0x14009775e  mov     dword ptr [rdi], 0
0x140097764  mov     qword ptr [rdi+8], 0
0x14009776c  cmp     [rsp+88h+arg_20], 0
0x140097774  jz      short loc_14009777D
0x140097776  mov     dword ptr [rdi+8], 1
0x14009777d  lea     r9, [rsp+88h+var_50]
0x140097782  mov     r8, rsi
0x140097785  xor     edx, edx
0x140097787  mov     rcx, rdi
0x14009778a  call    SkobCreateHandle
0x14009778f  mov     ebx, eax
0x140097791  test    eax, eax
0x140097793  js      short loc_1400977CB
0x140097795  mov     rdx, [rsp+88h+var_50]
0x14009779a  mov     rcx, r15
0x14009779d  call    RtlWriteULong64ToUser
0x1400977a2  jmp     short loc_1400977CB
0x1400977a4  mov     ebx, eax
0x1400977a6  mov     [rsp+88h+var_68], 0
0x1400977af  xor     r9d, r9d
0x1400977b2  xor     r8d, r8d
0x1400977b5  xor     edx, edx
0x1400977b7  mov     rcx, [rsp+88h+var_50]
0x1400977bc  call    SkobCloseHandleEx
0x1400977c1  mov     rsi, [rsp+88h+var_48]
0x1400977c6  mov     rdi, [rsp+88h+var_40]
0x1400977cb  mov     rcx, rdi
0x1400977ce  call    SkobDereferenceObject
0x1400977d3  test    ebx, ebx
0x1400977d5  jns     short loc_1400977E4
0x1400977d7  test    rsi, rsi
0x1400977da  jz      short loc_1400977E4
0x1400977dc  mov     rcx, rsi
0x1400977df  call    NkClose
0x1400977e4  mov     eax, ebx
0x1400977e6  mov     rbx, [rsp+88h+arg_8]
0x1400977ee  add     rsp, 60h
0x1400977f2  pop     r15
0x1400977f4  pop     r14
0x1400977f6  pop     r12
0x1400977f8  pop     rdi
0x1400977f9  pop     rsi
0x1400977fa  retn
```
