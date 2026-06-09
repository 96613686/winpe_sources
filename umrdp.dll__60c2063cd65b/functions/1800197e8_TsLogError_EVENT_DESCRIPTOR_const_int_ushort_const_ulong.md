# TsLogError(_EVENT_DESCRIPTOR const &,int,ushort * * const,ulong)

- ea: `0x1800197e8`
- end: `0x18001987e`
- name: `?TsLogError@@YAXAEBU_EVENT_DESCRIPTOR@@HQEAPEAGK@Z`
- size: `150`
- prototype: `void __fastcall(const struct _EVENT_DESCRIPTOR *, int, unsigned __int16 **const, unsigned int)`
- caller_count: `16`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800032f0`
- `0x180004680`
- `0x180007f4c`
- `0x1800085bc`
- `0x18000a5cc`
- `0x18000e5c0`
- `0x1800101ec`
- `0x180010904`
- `0x180011850`
- `0x180012d5c`
- `0x1800140a4`
- `0x1800149b0`
- `0x180015428`
- `0x180015cd8`
- `0x1800169a0`
- `0x180019224`

## callees

- `0x1800197e8`
- `0x180047ef0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001985d`
- `ntdll!EtwEventWrite` at `0x18001985d`

## pseudocode

```c
void __fastcall TsLogError(const struct _EVENT_DESCRIPTOR *a1, unsigned int a2, unsigned __int16 **const a3)
{
  __int64 v4; // rcx
  unsigned int i; // r8d
  __int64 v7; // rax
  unsigned __int16 *v8; // r10
  __int64 v9; // r9
  _QWORD v10[8]; // [rsp+20h] [rbp-58h] BYREF

  v4 = qword_18005DE60;
  if ( qword_18005DE60 )
  {
    for ( i = 0; (int)i < (int)a2; HIDWORD(v10[v9 + 1]) = 0 )
    {
      v7 = -1;
      v8 = a3[i];
      do
        ++v7;
      while ( v8[v7] );
      v9 = 2LL * i++;
      v10[v9] = v8;
      LODWORD(v10[v9 + 1]) = 2 * v7 + 2;
    }
    EtwEventWrite(v4, a1, a2, v10);
  }
}

```

## disassembly

```asm
0x1800197e8  mov     [rsp+arg_10], rbx
0x1800197ed  push    rdi
0x1800197ee  sub     rsp, 70h
0x1800197f2  mov     rax, cs:__security_cookie
0x1800197f9  xor     rax, rsp
0x1800197fc  mov     [rsp+78h+var_18], rax
0x180019801  mov     r11, rcx
0x180019804  xor     edi, edi
0x180019806  mov     rcx, cs:qword_18005DE60
0x18001980d  mov     rbx, r8
0x180019810  test    rcx, rcx
0x180019813  jz      short loc_180019863
0x180019815  mov     r8d, edi
0x180019818  test    edx, edx
0x18001981a  jle     short loc_180019852
0x18001981c  mov     r9d, r8d
0x18001981f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019823  mov     r10, [rbx+r9*8]
0x180019827  inc     rax
0x18001982a  cmp     [r10+rax*2], di
0x18001982f  jnz     short loc_180019827
0x180019831  add     r9, r9
0x180019834  lea     eax, ds:2[rax*2]
0x18001983b  inc     r8d
0x18001983e  mov     [rsp+r9*8+78h+var_58], r10
0x180019843  mov     [rsp+r9*8+78h+var_50], eax
0x180019848  mov     [rsp+r9*8+78h+var_4C], edi
0x18001984d  cmp     r8d, edx
0x180019850  jl      short loc_18001981C
0x180019852  mov     r8d, edx
0x180019855  lea     r9, [rsp+78h+var_58]
0x18001985a  mov     rdx, r11
0x18001985d  call    cs:__imp_EtwEventWrite
0x180019863  mov     rcx, [rsp+78h+var_18]
0x180019868  xor     rcx, rsp; StackCookie
0x18001986b  call    __security_check_cookie
0x180019870  mov     rbx, [rsp+78h+arg_10]
0x180019878  add     rsp, 70h
0x18001987c  pop     rdi
0x18001987d  retn
```
