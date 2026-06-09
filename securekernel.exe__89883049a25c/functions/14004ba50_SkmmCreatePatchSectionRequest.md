# SkmmCreatePatchSectionRequest

- ea: `0x14004ba50`
- end: `0x14004bbae`
- name: `SkmmCreatePatchSectionRequest`
- size: `350`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140043038`

## callees

- `0x14001d5e0`
- `0x14001e518`
- `0x14001e5e0`
- `0x140048b08`
- `0x14004ba50`
- `0x140080bac`
- `0x1400fcb48`

## pseudocode

```c
__int64 __fastcall SkmmCreatePatchSectionRequest(__int64 a1)
{
  _QWORD *StackBase; // rax
  __int64 v4; // rcx
  __int64 locked; // rax
  __int64 v6; // rdi
  int v7; // ebx
  char v8; // bp
  __int64 VadEntry; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // eax
  UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-28h] BYREF
  int v14; // [rsp+50h] [rbp+8h] BYREF
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  v14 = 0;
  v15 = 0;
  *(_QWORD *)&UnicodeString.Length = 0;
  UnicodeString.Buffer = 0;
  if ( (*(_DWORD *)(a1 + 12) & 0xF0) == 0 )
    return 3221225485LL;
  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
    v4 = StackBase[10];
  else
    v4 = 0;
  locked = SkmiObtainLockedVad(v4, *(_QWORD *)(a1 + 24) >> 12);
  v6 = locked;
  if ( !locked )
    return 3221225496LL;
  if ( (*(_QWORD *)(locked + 48) & 0x100000000000000LL) != 0 )
  {
    v7 = -1073741800;
    v8 = 1;
  }
  else
  {
    v8 = 0;
    if ( (*(unsigned int *)(locked + 24) | ((unsigned __int64)(*(_DWORD *)(locked + 32) & 0xFFF) << 32)) << 12 == *(_QWORD *)(a1 + 24) )
    {
      VadEntry = SkmiFindVadEntry(locked, 1);
      if ( VadEntry )
      {
        *(_QWORD *)(v6 + 48) = v11 | v10;
        v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, int *, UNICODE_STRING *))SkmiFindLatestHotPatchRecord)(
                *(unsigned int *)(VadEntry + 60),
                *(unsigned int *)(VadEntry + 56),
                &v14,
                &UnicodeString);
        v7 = v12;
        if ( v12 >= 0 )
        {
          v7 = SkmiOpenHotPatchFile(a1, &UnicodeString, &v15);
          if ( v7 >= 0 )
          {
            v7 = 0;
            *(_QWORD *)(a1 + 32) = v15;
          }
        }
        else if ( v12 == -1073741275 )
        {
          v7 = -1073740588;
        }
      }
      else
      {
        v7 = -1073741637;
      }
    }
    else
    {
      v7 = -1073741800;
    }
  }
  RtlFreeUnicodeString(&UnicodeString);
  if ( !v8 )
    *(_QWORD *)(v6 + 48) &= ~0x100000000000000uLL;
  SkmiUnlockAndDereferenceVad(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14004ba50  mov     rax, rsp
0x14004ba53  mov     [rax+18h], rbx
0x14004ba57  push    rbp
0x14004ba58  push    rsi
0x14004ba59  push    rdi
0x14004ba5a  sub     rsp, 30h
0x14004ba5e  mov     dword ptr [rax+8], 0
0x14004ba65  mov     rsi, rcx
0x14004ba68  mov     qword ptr [rax+10h], 0
0x14004ba70  mov     qword ptr [rax-28h], 0
0x14004ba78  mov     qword ptr [rax-20h], 0
0x14004ba80  mov     eax, [rcx+0Ch]
0x14004ba83  test    al, 0F0h
0x14004ba85  jnz     short loc_14004BA91
0x14004ba87  mov     eax, 0C000000Dh
0x14004ba8c  jmp     loc_14004BBA0
0x14004ba91  mov     rax, gs:8
0x14004ba9a  test    rax, rax
0x14004ba9d  jz      short loc_14004BAA5
0x14004ba9f  mov     rcx, [rax+50h]
0x14004baa3  jmp     short loc_14004BAA7
0x14004baa5  xor     ecx, ecx
0x14004baa7  mov     rdx, [rsi+18h]
0x14004baab  shr     rdx, 0Ch
0x14004baaf  call    SkmiObtainLockedVad
0x14004bab4  mov     rdi, rax
0x14004bab7  test    rax, rax
0x14004baba  jnz     short loc_14004BAC6
0x14004babc  mov     eax, 0C0000018h
0x14004bac1  jmp     loc_14004BBA0
0x14004bac6  mov     r8, [rax+30h]
0x14004baca  mov     r9, 100000000000000h
0x14004bad4  test    r9, r8
0x14004bad7  jz      short loc_14004BAE6
0x14004bad9  mov     ebx, 0C0000018h
0x14004bade  mov     bpl, 1
0x14004bae1  jmp     loc_14004BB79
0x14004bae6  mov     ecx, [rax+20h]
0x14004bae9  xor     bpl, bpl
0x14004baec  mov     eax, [rax+18h]
0x14004baef  and     ecx, 0FFFh
0x14004baf5  shl     rcx, 20h
0x14004baf9  or      rcx, rax
0x14004bafc  shl     rcx, 0Ch
0x14004bb00  cmp     rcx, [rsi+18h]
0x14004bb04  jz      short loc_14004BB0D
0x14004bb06  mov     ebx, 0C0000018h
0x14004bb0b  jmp     short loc_14004BB79
0x14004bb0d  mov     edx, 1
0x14004bb12  mov     rcx, rdi
0x14004bb15  call    SkmiFindVadEntry
0x14004bb1a  test    rax, rax
0x14004bb1d  jnz     short loc_14004BB26
0x14004bb1f  mov     ebx, 0C00000BBh
0x14004bb24  jmp     short loc_14004BB79
0x14004bb26  or      r8, r9
0x14004bb29  lea     r9, [rsp+48h+UnicodeString]
0x14004bb2e  mov     [rdi+30h], r8
0x14004bb32  lea     r8, [rsp+48h+arg_0]
0x14004bb37  mov     edx, [rax+38h]
0x14004bb3a  mov     ecx, [rax+3Ch]
0x14004bb3d  call    SkmiFindLatestHotPatchRecord
0x14004bb42  mov     ebx, eax
0x14004bb44  test    eax, eax
0x14004bb46  jns     short loc_14004BB56
0x14004bb48  cmp     eax, 0C0000225h
0x14004bb4d  jnz     short loc_14004BB79
0x14004bb4f  mov     ebx, 0C00004D4h
0x14004bb54  jmp     short loc_14004BB79
0x14004bb56  lea     r8, [rsp+48h+arg_8]
0x14004bb5b  mov     rcx, rsi
0x14004bb5e  lea     rdx, [rsp+48h+UnicodeString]
0x14004bb63  call    SkmiOpenHotPatchFile
0x14004bb68  mov     ebx, eax
0x14004bb6a  test    eax, eax
0x14004bb6c  js      short loc_14004BB79
0x14004bb6e  mov     rax, [rsp+48h+arg_8]
0x14004bb73  xor     ebx, ebx
0x14004bb75  mov     [rsi+20h], rax
0x14004bb79  lea     rcx, [rsp+48h+UnicodeString]; UnicodeString
0x14004bb7e  call    RtlFreeUnicodeString
0x14004bb83  test    bpl, bpl
0x14004bb86  jnz     short loc_14004BB96
0x14004bb88  mov     rax, 0FEFFFFFFFFFFFFFFh
0x14004bb92  and     [rdi+30h], rax
0x14004bb96  mov     rcx, rdi
0x14004bb99  call    SkmiUnlockAndDereferenceVad
0x14004bb9e  mov     eax, ebx
0x14004bba0  mov     rbx, [rsp+48h+arg_10]
0x14004bba5  add     rsp, 30h
0x14004bba9  pop     rdi
0x14004bbaa  pop     rsi
0x14004bbab  pop     rbp
0x14004bbac  retn
```
