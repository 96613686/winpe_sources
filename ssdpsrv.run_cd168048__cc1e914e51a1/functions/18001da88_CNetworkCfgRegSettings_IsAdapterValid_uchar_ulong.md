# CNetworkCfgRegSettings::IsAdapterValid(uchar *,ulong)

- ea: `0x18001da88`
- end: `0x18001db7a`
- name: `?IsAdapterValid@CNetworkCfgRegSettings@@QEAAHPEAEK@Z`
- size: `242`
- prototype: `__int64 __fastcall(CNetworkCfgRegSettings *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e064`

## callees

- `0x180011c44`
- `0x18001da88`
- `0x1800287d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001db57`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001db57`

## pseudocode

```c
__int64 __fastcall CNetworkCfgRegSettings::IsAdapterValid(
        CNetworkCfgRegSettings *this,
        unsigned __int8 *a2,
        unsigned int a3)
{
  unsigned int v7; // ebp
  __int64 v8; // r14
  char *v9; // rdi
  unsigned int v10; // ebx
  int v11; // esi
  int i; // edi
  char v13[32]; // [rsp+20h] [rbp-58h] BYREF

  if ( !a3 )
    return 1;
  v7 = 25;
  v13[0] = 0;
  v8 = 0;
  v9 = v13;
  v10 = 1;
  do
  {
    if ( v7 < 3 )
      break;
    StringCchPrintfA(v9, 3u, "%02x-", a2[v8]);
    v9 += 3;
    v7 -= 3;
    v8 = (unsigned int)(v8 + 1);
  }
  while ( (unsigned int)v8 < a3 );
  if ( v9 != v13 )
    *(v9 - 1) = 0;
  if ( v13[0] )
  {
    v11 = *((_DWORD *)this + 4);
    for ( i = 0; i < v11; ++i )
    {
      if ( !(unsigned int)_o__stricmp(*((_QWORD *)this + 1) + 25LL * i, v13) )
        return v10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001da88  mov     [rsp+arg_10], rbx
0x18001da8d  mov     [rsp+arg_18], rbp
0x18001da92  push    rsi
0x18001da93  push    rdi
0x18001da94  push    r12
0x18001da96  push    r14
0x18001da98  push    r15
0x18001da9a  sub     rsp, 50h
0x18001da9e  mov     rax, cs:__security_cookie
0x18001daa5  xor     rax, rsp
0x18001daa8  mov     [rsp+78h+var_38], rax
0x18001daad  mov     esi, r8d
0x18001dab0  mov     r12, rdx
0x18001dab3  mov     r15, rcx
0x18001dab6  test    r8d, r8d
0x18001dab9  jnz     short loc_18001DAE6
0x18001dabb  lea     eax, [r8+1]
0x18001dabf  mov     rcx, [rsp+78h+var_38]
0x18001dac4  xor     rcx, rsp; StackCookie
0x18001dac7  call    __security_check_cookie
0x18001dacc  lea     r11, [rsp+78h+var_28]
0x18001dad1  mov     rbx, [r11+40h]
0x18001dad5  mov     rbp, [r11+48h]
0x18001dad9  mov     rsp, r11
0x18001dadc  pop     r15
0x18001dade  pop     r14
0x18001dae0  pop     r12
0x18001dae2  pop     rdi
0x18001dae3  pop     rsi
0x18001dae4  retn
0x18001dae6  mov     ebp, 19h
0x18001daeb  mov     [rsp+78h+var_58], 0
0x18001daf0  xor     r14d, r14d
0x18001daf3  lea     rdi, [rsp+78h+var_58]
0x18001daf8  lea     ebx, [rbp-18h]
0x18001dafb  test    esi, esi
0x18001dafd  jz      short loc_18001DB36
0x18001daff  cmp     ebp, 3
0x18001db02  jb      short loc_18001DB2C
0x18001db04  movzx   r9d, byte ptr [r14+r12]
0x18001db09  lea     r8, a02x; "%02x-"
0x18001db10  mov     edx, 3; unsigned __int64
0x18001db15  mov     rcx, rdi; char *
0x18001db18  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001db1d  add     rdi, 3
0x18001db21  add     ebp, 0FFFFFFFDh
0x18001db24  add     r14d, ebx
0x18001db27  cmp     r14d, esi
0x18001db2a  jb      short loc_18001DAFF
0x18001db2c  lea     rax, [rsp+78h+var_58]
0x18001db31  cmp     rdi, rax
0x18001db34  jnz     short loc_18001DB74
0x18001db36  cmp     [rsp+78h+var_58], 0
0x18001db3b  jz      short loc_18001DB6B
0x18001db3d  mov     esi, [r15+10h]
0x18001db41  xor     edi, edi
0x18001db43  cmp     edi, esi
0x18001db45  jge     short loc_18001DB6B
0x18001db47  movsxd  rax, edi
0x18001db4a  lea     rdx, [rsp+78h+var_58]
0x18001db4f  imul    rcx, rax, 19h
0x18001db53  add     rcx, [r15+8]
0x18001db57  call    cs:__imp__o__stricmp
0x18001db5e  nop     dword ptr [rax+rax+00h]
0x18001db63  test    eax, eax
0x18001db65  jz      short loc_18001DB6D
0x18001db67  add     edi, ebx
0x18001db69  jmp     short loc_18001DB43
0x18001db6b  xor     ebx, ebx
0x18001db6d  mov     eax, ebx
0x18001db6f  jmp     loc_18001DABF
0x18001db74  mov     byte ptr [rdi-1], 0
0x18001db78  jmp     short loc_18001DB36
```
