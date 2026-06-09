# WbemStringCopy(ushort const *)

- ea: `0x180009e20`
- end: `0x180009f2c`
- name: `?WbemStringCopy@@YAPEAGPEBG@Z`
- size: `268`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009780`
- `0x1800099b0`
- `0x180009c40`

## callees

- `0x180009e20`
- `0x180013564`
- `0x180014120`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009e56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009e56`

## pseudocode

```c
unsigned __int16 *__fastcall WbemStringCopy(const unsigned __int16 *a1)
{
  const unsigned __int16 *v1; // rbx
  __int64 v2; // rax
  unsigned __int64 v4; // rdi
  _WORD *v5; // rax
  _WORD *v6; // rsi
  __int64 v7; // rax
  _WORD *v8; // rcx
  _WORD *v9; // rax
  unsigned int v10; // ebx

  v1 = a1;
  if ( a1 )
  {
    v2 = -1;
    while ( a1[++v2] != 0 )
      ;
    v4 = v2 + 1;
    v5 = CoTaskMemAlloc(2 * (v2 + 1));
    v6 = v5;
    if ( v5 )
    {
      if ( v4 )
      {
        if ( v4 > 0x7FFFFFFF )
        {
          v10 = -2147024809;
          *v5 = 0;
        }
        else
        {
          v7 = 2147483646;
          v8 = v6;
          do
          {
            if ( !v7 )
              break;
            if ( !*v1 )
              break;
            *v8++ = *v1++;
            --v7;
            --v4;
          }
          while ( v4 );
          v9 = v8 - 1;
          v10 = -2147024774;
          if ( v4 )
          {
            v9 = v8;
            v10 = 0;
          }
          *v9 = 0;
          if ( v4 )
            return v6;
        }
      }
      else
      {
        v10 = -2147024809;
      }
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v10);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2122daa7e8023666a1921e333e1159b1_Traceguids, v10);
      }
      return v6;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009e20  mov     [rsp+arg_0], rbx
0x180009e25  mov     [rsp+arg_8], rsi
0x180009e2a  push    rdi
0x180009e2b  sub     rsp, 20h
0x180009e2f  mov     rbx, rcx
0x180009e32  test    rcx, rcx
0x180009e35  jz      loc_180009ECB
0x180009e3b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009e42  cmp     word ptr [rcx+rax*2+2], 0
0x180009e48  lea     rax, [rax+1]
0x180009e4c  jnz     short loc_180009E42
0x180009e4e  lea     rdi, [rax+1]
0x180009e52  lea     rcx, [rdi+rdi]; cb
0x180009e56  call    cs:__imp_CoTaskMemAlloc
0x180009e5c  mov     rsi, rax
0x180009e5f  test    rax, rax
0x180009e62  jz      short loc_180009ECB
0x180009e64  test    rdi, rdi
0x180009e67  jz      short loc_180009ECF
0x180009e69  cmp     rdi, 7FFFFFFFh
0x180009e70  ja      short loc_180009EDB
0x180009e72  mov     eax, 7FFFFFFEh
0x180009e77  mov     rcx, rsi
0x180009e7a  test    rax, rax
0x180009e7d  jz      short loc_180009E9B
0x180009e7f  movzx   edx, word ptr [rbx]
0x180009e82  test    dx, dx
0x180009e85  jz      short loc_180009E9B
0x180009e87  mov     [rcx], dx
0x180009e8a  add     rbx, 2
0x180009e8e  add     rcx, 2
0x180009e92  dec     rax
0x180009e95  sub     rdi, 1
0x180009e99  jnz     short loc_180009E7A
0x180009e9b  test    rdi, rdi
0x180009e9e  lea     rax, [rcx-2]
0x180009ea2  mov     ebx, 8007007Ah
0x180009ea7  cmovnz  rax, rcx
0x180009eab  xor     ecx, ecx
0x180009ead  test    rdi, rdi
0x180009eb0  cmovnz  ebx, ecx
0x180009eb3  mov     [rax], cx
0x180009eb6  jz      short loc_180009EE5
0x180009eb8  mov     rax, rsi
0x180009ebb  mov     rbx, [rsp+28h+arg_0]
0x180009ec0  mov     rsi, [rsp+28h+arg_8]
0x180009ec5  add     rsp, 20h
0x180009ec9  pop     rdi
0x180009eca  retn
0x180009ecb  xor     eax, eax
0x180009ecd  jmp     short loc_180009EBB
0x180009ecf  mov     ebx, 80070057h
0x180009ed4  test    rdi, rdi
0x180009ed7  jnz     short loc_180009EE0
0x180009ed9  jmp     short loc_180009EE5
0x180009edb  mov     ebx, 80070057h
0x180009ee0  xor     ecx, ecx
0x180009ee2  mov     [rax], cx
0x180009ee5  mov     edx, ebx; int
0x180009ee7  lea     rcx, qword_18006A9C0; this
0x180009eee  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009ef3  mov     rcx, cs:WPP_GLOBAL_Control
0x180009efa  lea     rax, WPP_GLOBAL_Control
0x180009f01  cmp     rcx, rax
0x180009f04  jz      short loc_180009EB8
0x180009f06  test    byte ptr [rcx+1Ch], 1
0x180009f0a  jz      short loc_180009EB8
0x180009f0c  cmp     byte ptr [rcx+19h], 2
0x180009f10  jb      short loc_180009EB8
0x180009f12  mov     rcx, [rcx+10h]
0x180009f16  lea     r8, WPP_2122daa7e8023666a1921e333e1159b1_Traceguids
0x180009f1d  mov     edx, 0Ah
0x180009f22  mov     r9d, ebx
0x180009f25  call    WPP_SF_D
0x180009f2a  jmp     short loc_180009EB8
```
