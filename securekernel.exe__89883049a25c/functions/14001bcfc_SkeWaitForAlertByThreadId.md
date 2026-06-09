# SkeWaitForAlertByThreadId

- ea: `0x14001bcfc`
- end: `0x14001be7c`
- name: `SkeWaitForAlertByThreadId`
- size: `384`
- prototype: ``
- caller_count: `9`
- callee_count: `6`
- tags: ``

## callers

- `0x14000b0b0`
- `0x1400147b4`
- `0x140034ccc`
- `0x1400670f0`
- `0x14006b284`
- `0x140085510`
- `0x140097b94`
- `0x140098898`
- `0x1400ff160`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x14001bcfc`
- `0x1400ee8b0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkeWaitForAlertByThreadId(char a1, __int64 *a2)
{
  __int64 v3; // r14
  volatile signed __int32 *StackBase; // rbx
  char v5; // si
  __int64 v6; // rdx
  unsigned int v7; // edi
  unsigned int v9; // [rsp+20h] [rbp-59h] BYREF
  __int64 v10; // [rsp+28h] [rbp-51h]
  __int64 v11; // [rsp+30h] [rbp-49h]
  __int64 v12; // [rsp+38h] [rbp-41h]

  v3 = a1;
  memset_0(&v9, 0, 0x68u);
  StackBase = (volatile signed __int32 *)KeGetPcr()->NtTib.StackBase;
  v5 = 0;
  LOBYTE(v6) = SkAcquireSpinLockExclusive(StackBase + 4);
  if ( !_interlockedbittestandreset(StackBase + 43, 8u) )
  {
    while ( (_BYTE)v3 != 1 || (StackBase[43] & 2) == 0 )
    {
      _InterlockedOr(StackBase + 43, 0x80u);
      *((_BYTE *)StackBase + 32) = v3;
      SkReleaseSpinLockExclusive(StackBase + 4, v6);
      BYTE1(v9) = 0;
      HIWORD(v9) = 8;
      v10 = v3;
      if ( a2 )
      {
        v12 = *a2;
        v11 = 1;
      }
      else
      {
        v11 = 0;
      }
      SkCallNormalMode(&v9);
      v7 = v10;
      LOBYTE(v6) = SkAcquireSpinLockExclusive(StackBase + 4);
      _InterlockedAnd(StackBase + 43, 0xFFFFFF7F);
      if ( v7 == 258 )
      {
        v5 = BYTE1(*((_DWORD *)StackBase + 43)) & 1;
        goto LABEL_14;
      }
      if ( (StackBase[43] & 0x100) == 0 )
        _InterlockedOr(StackBase + 43, 0x200u);
      if ( _interlockedbittestandreset(StackBase + 43, 8u) )
        break;
    }
  }
  v7 = 257;
LABEL_14:
  SkReleaseSpinLockExclusive(StackBase + 4, v6);
  if ( v5 )
  {
    BYTE1(v9) = 0;
    HIWORD(v9) = 8;
    v10 = v3;
    v11 = 1;
    v12 = 0;
    SkCallNormalMode(&v9);
  }
  return v7;
}

```

## disassembly

```asm
0x14001bcfc  push    rbp
0x14001bcfe  push    rbx
0x14001bcff  push    rsi
0x14001bd00  push    rdi
0x14001bd01  push    r12
0x14001bd03  push    r14
0x14001bd05  push    r15
0x14001bd07  lea     rbp, [rsp-27h]
0x14001bd0c  sub     rsp, 0A0h
0x14001bd13  mov     rax, cs:__security_cookie
0x14001bd1a  xor     rax, rsp
0x14001bd1d  mov     [rbp+57h+var_40], rax
0x14001bd21  mov     r12, rdx
0x14001bd24  movsx   r14, cl
0x14001bd28  xor     edx, edx; Val
0x14001bd2a  lea     rcx, [rbp+57h+var_B0]; void *
0x14001bd2e  lea     r8d, [rdx+68h]; Size
0x14001bd32  call    memset_0
0x14001bd37  mov     rbx, gs:8
0x14001bd40  xor     sil, sil
0x14001bd43  lea     r15, [rbx+10h]
0x14001bd47  mov     rcx, r15
0x14001bd4a  call    SkAcquireSpinLockExclusive
0x14001bd4f  lock btr dword ptr [rbx+0ACh], 8
0x14001bd58  mov     dl, al
0x14001bd5a  mov     edi, 8
0x14001bd5f  jb      loc_14001BE1F
0x14001bd65  cmp     r14b, 1
0x14001bd69  jnz     short loc_14001BD79
0x14001bd6b  mov     eax, [rbx+0ACh]
0x14001bd71  test    al, 2
0x14001bd73  jnz     loc_14001BE1F
0x14001bd79  lock or dword ptr [rbx+0ACh], 80h
0x14001bd84  mov     rcx, r15
0x14001bd87  mov     [rbx+20h], r14b
0x14001bd8b  call    SkReleaseSpinLockExclusive
0x14001bd90  mov     [rbp+57h+var_AF], sil
0x14001bd94  mov     [rbp+57h+var_AE], di
0x14001bd98  mov     [rbp+57h+var_A8], r14
0x14001bd9c  test    r12, r12
0x14001bd9f  jz      short loc_14001BDB3
0x14001bda1  mov     rax, [r12]
0x14001bda5  mov     [rbp+57h+var_98], rax
0x14001bda9  mov     [rbp+57h+var_A0], 1
0x14001bdb1  jmp     short loc_14001BDBB
0x14001bdb3  mov     [rbp+57h+var_A0], 0
0x14001bdbb  lea     rcx, [rbp+57h+var_B0]
0x14001bdbf  call    SkCallNormalMode
0x14001bdc4  mov     edi, dword ptr [rbp+57h+var_A8]
0x14001bdc7  mov     rcx, r15
0x14001bdca  call    SkAcquireSpinLockExclusive
0x14001bdcf  mov     dl, al
0x14001bdd1  lock and dword ptr [rbx+0ACh], 0FFFFFF7Fh
0x14001bddc  cmp     edi, 102h
0x14001bde2  jz      short loc_14001BE10
0x14001bde4  mov     eax, [rbx+0ACh]
0x14001bdea  bt      eax, 8
0x14001bdee  jb      short loc_14001BDFB
0x14001bdf0  lock or dword ptr [rbx+0ACh], 200h
0x14001bdfb  lock btr dword ptr [rbx+0ACh], 8
0x14001be04  jb      short loc_14001BE1F
0x14001be06  mov     edi, 8
0x14001be0b  jmp     loc_14001BD65
0x14001be10  mov     esi, [rbx+0ACh]
0x14001be16  shr     esi, 8
0x14001be19  and     sil, 1
0x14001be1d  jmp     short loc_14001BE24
0x14001be1f  mov     edi, 101h
0x14001be24  mov     rcx, r15
0x14001be27  call    SkReleaseSpinLockExclusive
0x14001be2c  test    sil, sil
0x14001be2f  jz      short loc_14001BE5B
0x14001be31  mov     eax, 8
0x14001be36  mov     [rbp+57h+var_AF], 0
0x14001be3a  lea     rcx, [rbp+57h+var_B0]
0x14001be3e  mov     [rbp+57h+var_AE], ax
0x14001be42  mov     [rbp+57h+var_A8], r14
0x14001be46  mov     [rbp+57h+var_A0], 1
0x14001be4e  mov     [rbp+57h+var_98], 0
0x14001be56  call    SkCallNormalMode
0x14001be5b  mov     eax, edi
0x14001be5d  mov     rcx, [rbp+57h+var_40]
0x14001be61  xor     rcx, rsp; StackCookie
0x14001be64  call    __security_check_cookie
0x14001be69  add     rsp, 0A0h
0x14001be70  pop     r15
0x14001be72  pop     r14
0x14001be74  pop     r12
0x14001be76  pop     rdi
0x14001be77  pop     rsi
0x14001be78  pop     rbx
0x14001be79  pop     rbp
0x14001be7a  retn
```
