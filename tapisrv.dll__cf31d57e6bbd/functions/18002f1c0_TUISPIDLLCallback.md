# TUISPIDLLCallback

- ea: `0x18002f1c0`
- end: `0x18002f408`
- name: `TUISPIDLLCallback`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180028100`

## callees

- `0x180006f24`
- `0x180007244`
- `0x18001f494`
- `0x180021640`
- `0x18002f1c0`
- `0x18003e15c`
- `0x18003e3b4`
- `0x180040010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002f316`
- `KERNEL32!LeaveCriticalSection` at `0x18002f316`

## pseudocode

```c
__int64 __fastcall TUISPIDLLCallback(unsigned __int64 a1, _DWORD *a2, unsigned int a3, __int64 a4, _DWORD *a5)
{
  __int64 v7; // r14
  unsigned int *v8; // r12
  unsigned int *v9; // r13
  __int64 result; // rax
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64, _QWORD); // rsi
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  char *LineLookupEntry; // rax
  __int64 v16; // rax
  int v17; // edx
  int v18; // ecx

  v7 = (unsigned int)a2[2];
  v8 = a2 + 4;
  v9 = a2 + 5;
  result = IsBadSizeOffset(a3, 0, a2[5], a2[4], 4);
  if ( (_DWORD)result )
    goto LABEL_34;
  v11 = 0;
  if ( a2[3] == 1 )
  {
    if ( (dword_180051900 & 2) == 0 || (*(_BYTE *)(a1 + 216) & 1) != 0 )
      goto LABEL_25;
    result = (unsigned int)a2[2];
    if ( (unsigned int)result < *(_DWORD *)(a1 + 96) )
    {
      v7 = *(unsigned int *)(*(_QWORD *)(a1 + 88) + 4LL * (unsigned int)result);
LABEL_25:
      LineLookupEntry = GetLineLookupEntry(v7);
      goto LABEL_26;
    }
LABEL_34:
    *a2 = -2147483576;
    return result;
  }
  if ( a2[3] != 2 )
  {
    if ( a2[3] == 3 )
    {
      if ( WaitForExclusiveClientAccess(a1) )
      {
        v14 = *(_QWORD *)(a1 + 184);
        if ( v14 )
        {
          while ( a2[2] != *(_DWORD *)(v14 + 20) )
          {
            v14 = *(_QWORD *)(v14 + 80);
            if ( !v14 )
              goto LABEL_14;
          }
          v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(v14 + 32);
        }
LABEL_14:
        LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (a1 >> 4)));
      }
    }
    else if ( a2[3] == 4 )
    {
      v12 = ReferenceObject((unsigned int)(a2[3] - 3), (unsigned int)a2[2], 1196379204);
      if ( v12 )
      {
        v7 = *(_QWORD *)(v12 + 48);
        v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)(v12 + 40) + 976LL);
        DereferenceObject(v13, a2[2], 1);
      }
    }
    goto LABEL_29;
  }
  if ( (dword_180051900 & 2) != 0 && (*(_BYTE *)(a1 + 216) & 1) == 0 )
  {
    result = (unsigned int)a2[2];
    if ( (unsigned int)result >= *(_DWORD *)(a1 + 120) )
    {
      *a2 = -1879048164;
      return result;
    }
    v7 = *(unsigned int *)(*(_QWORD *)(a1 + 112) + 4LL * (unsigned int)a2[2]);
  }
  LineLookupEntry = GetPhoneLookupEntry(v7);
LABEL_26:
  if ( LineLookupEntry )
  {
    v16 = *((_QWORD *)LineLookupEntry + 3);
    if ( v16 )
      v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(v16 + 976);
  }
LABEL_29:
  if ( v11 )
  {
    result = v11(v7, (unsigned int)a2[3], a4 + *v8, *v9);
    if ( !(_DWORD)result )
    {
      v17 = *v8;
      a2[6] = *v8;
      v18 = *v9;
      a2[7] = *v9;
      *a5 = v18 + 60 + v17;
    }
  }
  else
  {
    result = 2147483720LL;
  }
  *a2 = result;
  return result;
}

```

## disassembly

```asm
0x18002f1c0  mov     r11, rsp
0x18002f1c3  mov     [r11+8], rbx
0x18002f1c7  mov     [r11+18h], rsi
0x18002f1cb  mov     [r11+20h], r9
0x18002f1cf  mov     [r11+10h], rdx
0x18002f1d3  push    rdi
0x18002f1d4  push    r12
0x18002f1d6  push    r13
0x18002f1d8  push    r14
0x18002f1da  push    r15
0x18002f1dc  sub     rsp, 60h
0x18002f1e0  mov     eax, r8d
0x18002f1e3  mov     rbx, rdx
0x18002f1e6  mov     rdi, rcx
0x18002f1e9  mov     r14d, [rdx+8]
0x18002f1ed  mov     [r11-50h], r14
0x18002f1f1  lea     r12, [rdx+10h]
0x18002f1f5  mov     [rsp+88h+var_48], r12
0x18002f1fa  lea     r13, [rdx+14h]
0x18002f1fe  mov     [rsp+88h+var_40], r13
0x18002f203  mov     [rsp+88h+var_68], 4
0x18002f20b  mov     r9d, [r12]
0x18002f20f  mov     r8d, [r13+0]
0x18002f213  xor     edx, edx
0x18002f215  mov     ecx, eax
0x18002f217  call    IsBadSizeOffset
0x18002f21c  test    eax, eax
0x18002f21e  jnz     loc_18002F3E8
0x18002f224  xor     esi, esi
0x18002f226  mov     [rsp+88h+var_58], rsi
0x18002f22b  lea     r15, [rbx+0Ch]
0x18002f22f  mov     [rsp+88h+var_38], r15
0x18002f234  mov     ecx, [r15]
0x18002f237  sub     ecx, 1
0x18002f23a  jz      loc_18002F358
0x18002f240  sub     ecx, 1
0x18002f243  jz      loc_18002F31E
0x18002f249  sub     ecx, 1
0x18002f24c  jz      short loc_18002F2C6
0x18002f24e  cmp     ecx, 1
0x18002f251  jnz     loc_18002F399
0x18002f257  mov     r8d, 474F4C44h
0x18002f25d  mov     edx, [rbx+8]
0x18002f260  call    ReferenceObject
0x18002f265  test    rax, rax
0x18002f268  jnz     short loc_18002F274
0x18002f26a  mov     [rsp+88h+var_58], rsi
0x18002f26f  jmp     loc_18002F399
0x18002f274  mov     r14, [rax+30h]
0x18002f278  mov     [rsp+88h+var_50], r14
0x18002f27d  mov     rax, [rax+28h]
0x18002f281  mov     rsi, [rax+3D0h]
0x18002f288  mov     [rsp+88h+var_58], rsi
0x18002f28d  mov     r8d, 1
0x18002f293  mov     edx, [rbx+8]
0x18002f296  call    DereferenceObject
0x18002f29b  jmp     loc_18002F399
0x18002f2a0  mov     rbx, [rsp+88h+arg_8]
0x18002f2a8  mov     r14, [rsp+88h+var_50]
0x18002f2ad  mov     rsi, [rsp+88h+var_58]
0x18002f2b2  mov     r12, [rsp+88h+var_48]
0x18002f2b7  mov     r13, [rsp+88h+var_40]
0x18002f2bc  mov     r15, [rsp+88h+var_38]
0x18002f2c1  jmp     loc_18002F399
0x18002f2c6  mov     rcx, rdi
0x18002f2c9  call    WaitForExclusiveClientAccess
0x18002f2ce  test    rax, rax
0x18002f2d1  jz      loc_18002F399
0x18002f2d7  mov     rax, [rdi+0B8h]
0x18002f2de  test    rax, rax
0x18002f2e1  jz      short loc_18002F2FA
0x18002f2e3  mov     ecx, [rbx+8]
0x18002f2e6  cmp     ecx, [rax+14h]
0x18002f2e9  jz      short loc_18002F2F6
0x18002f2eb  mov     rax, [rax+50h]
0x18002f2ef  test    rax, rax
0x18002f2f2  jnz     short loc_18002F2E6
0x18002f2f4  jmp     short loc_18002F2FA
0x18002f2f6  mov     rsi, [rax+20h]
0x18002f2fa  shr     rdi, 4
0x18002f2fe  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18002f304  and     rdi, rax
0x18002f307  lea     rcx, [rdi+rdi*4]
0x18002f30b  mov     rax, cs:gLockTable
0x18002f312  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18002f316  call    cs:__imp_LeaveCriticalSection
0x18002f31c  jmp     short loc_18002F399
0x18002f31e  test    byte ptr cs:dword_180051900, 2
0x18002f325  jz      short loc_18002F34E
0x18002f327  test    byte ptr [rdi+0D8h], 1
0x18002f32e  jnz     short loc_18002F34E
0x18002f330  mov     eax, [rbx+8]
0x18002f333  cmp     eax, [rdi+78h]
0x18002f336  jb      short loc_18002F343
0x18002f338  mov     dword ptr [rbx], 9000001Ch
0x18002f33e  jmp     loc_18002F3EE
0x18002f343  mov     rcx, rax
0x18002f346  mov     rax, [rdi+70h]
0x18002f34a  mov     r14d, [rax+rcx*4]
0x18002f34e  mov     ecx, r14d
0x18002f351  call    GetPhoneLookupEntry
0x18002f356  jmp     short loc_18002F384
0x18002f358  test    byte ptr cs:dword_180051900, 2
0x18002f35f  jz      short loc_18002F37C
0x18002f361  test    byte ptr [rdi+0D8h], 1
0x18002f368  jnz     short loc_18002F37C
0x18002f36a  mov     eax, [rbx+8]
0x18002f36d  cmp     eax, [rdi+60h]
0x18002f370  jnb     short loc_18002F3E8
0x18002f372  mov     ecx, eax
0x18002f374  mov     rax, [rdi+58h]
0x18002f378  mov     r14d, [rax+rcx*4]
0x18002f37c  mov     ecx, r14d
0x18002f37f  call    GetLineLookupEntry
0x18002f384  test    rax, rax
0x18002f387  jz      short loc_18002F399
0x18002f389  mov     rax, [rax+18h]
0x18002f38d  test    rax, rax
0x18002f390  jz      short loc_18002F399
0x18002f392  mov     rsi, [rax+3D0h]
0x18002f399  test    rsi, rsi
0x18002f39c  jz      short loc_18002F3DF
0x18002f39e  mov     r8d, [r12]
0x18002f3a2  add     r8, [rsp+88h+arg_18]
0x18002f3aa  mov     r9d, [r13+0]
0x18002f3ae  mov     edx, [r15]
0x18002f3b1  mov     rcx, r14
0x18002f3b4  mov     rax, rsi
0x18002f3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3bc  test    eax, eax
0x18002f3be  jnz     short loc_18002F3E4
0x18002f3c0  mov     edx, [r12]
0x18002f3c4  mov     [rbx+18h], edx
0x18002f3c7  mov     ecx, [r13+0]
0x18002f3cb  mov     [rbx+1Ch], ecx
0x18002f3ce  add     ecx, 3Ch ; '<'
0x18002f3d1  add     edx, ecx
0x18002f3d3  mov     rcx, [rsp+88h+arg_20]
0x18002f3db  mov     [rcx], edx
0x18002f3dd  jmp     short loc_18002F3E4
0x18002f3df  mov     eax, 80000048h
0x18002f3e4  mov     [rbx], eax
0x18002f3e6  jmp     short loc_18002F3EE
0x18002f3e8  mov     dword ptr [rbx], 80000048h
0x18002f3ee  lea     r11, [rsp+88h+var_28]
0x18002f3f3  mov     rbx, [r11+30h]
0x18002f3f7  mov     rsi, [r11+40h]
0x18002f3fb  mov     rsp, r11
0x18002f3fe  pop     r15
0x18002f400  pop     r14
0x18002f402  pop     r13
0x18002f404  pop     r12
0x18002f406  pop     rdi
0x18002f407  retn
```
