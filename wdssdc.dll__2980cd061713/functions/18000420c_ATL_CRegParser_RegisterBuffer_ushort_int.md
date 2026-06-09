# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000420c`
- end: `0x1800043b7`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `427`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800043c0`

## callees

- `0x1800015b0`
- `0x180003a70`
- `0x180003c7c`
- `0x18000420c`
- `0x18000459c`
- `0x18000cbb0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180004293`
- `KERNEL32!lstrcmpiW` at `0x180004293`
- `USER32!CharNextW` at `0x180004397`
- `USER32!CharNextW` at `0x180004397`
- `ole32!CoTaskMemFree` at `0x1800042b9`
- `ole32!CoTaskMemFree` at `0x1800042b9`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  unsigned int v8; // esi
  __int64 v9; // rbx
  LPCWSTR *v10; // r14
  HKEY v11; // rsi
  __int64 v12; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *(_QWORD *)this = pv;
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken(this, String1);
        if ( Token < 0 )
          break;
        v8 = 0;
        v9 = 0;
        v10 = (LPCWSTR *)&`ATL::CRegParser::HKeyFromString'::`2'::map;
        while ( lstrcmpiW(String1, *v10) )
        {
          ++v8;
          ++v9;
          v10 += 2;
          if ( v8 >= 0xE )
            goto LABEL_7;
        }
        v11 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v9 + 1);
        if ( !v11 )
          goto LABEL_7;
        Token = ATL::CRegParser::NextToken(this, String1);
        if ( Token < 0 )
          break;
        if ( String1[0] != 123 )
        {
LABEL_7:
          Token = -2147352567;
          break;
        }
        if ( a3 )
        {
          v12 = *(_QWORD *)this;
          Token = ATL::CRegParser::RegisterSubkeys(this, String1, v11, a3, 0);
          if ( Token < 0 )
          {
            *(_QWORD *)this = v12;
            ATL::CRegParser::RegisterSubkeys(this, String1, v11, 0, 0);
            break;
          }
        }
        else
        {
          Token = ATL::CRegParser::RegisterSubkeys(this, String1, v11, 0, 0);
          if ( Token < 0 )
            break;
        }
        while ( **(_WORD **)this == 9 || **(_WORD **)this == 10 || **(_WORD **)this == 13 || **(_WORD **)this == 32 )
          *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
      }
      while ( **(_WORD **)this );
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x18000420c  mov     [rsp+arg_18], rbx
0x180004211  push    rbp
0x180004212  push    rsi
0x180004213  push    rdi
0x180004214  push    r12
0x180004216  push    r13
0x180004218  push    r14
0x18000421a  push    r15
0x18000421c  mov     eax, 2050h
0x180004221  call    _alloca_probe
0x180004226  sub     rsp, rax
0x180004229  mov     rax, cs:__security_cookie
0x180004230  xor     rax, rsp
0x180004233  mov     [rsp+2088h+var_48], rax
0x18000423b  mov     r15d, r8d
0x18000423e  xor     r12d, r12d
0x180004241  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180004246  mov     [rsp+2088h+pv], r12
0x18000424b  mov     rdi, rcx
0x18000424e  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180004253  mov     ebx, eax
0x180004255  test    eax, eax
0x180004257  js      short loc_1800042C7
0x180004259  mov     rbp, [rsp+2088h+pv]
0x18000425e  mov     [rdi], rbp
0x180004261  cmp     r12w, [rbp+0]
0x180004266  jz      short loc_1800042B6
0x180004268  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000426f  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004274  mov     rcx, rdi; this
0x180004277  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000427c  mov     ebx, eax
0x18000427e  test    eax, eax
0x180004280  js      short loc_1800042B6
0x180004282  mov     esi, r12d
0x180004285  mov     rbx, r12
0x180004288  mov     r14, r13
0x18000428b  mov     rdx, [r14]; lpString2
0x18000428e  lea     rcx, [rsp+2088h+String1]; lpString1
0x180004293  call    cs:__imp_lstrcmpiW
0x18000429a  nop     dword ptr [rax+rax+00h]
0x18000429f  test    eax, eax
0x1800042a1  jz      short loc_1800042F3
0x1800042a3  inc     esi
0x1800042a5  inc     rbx
0x1800042a8  add     r14, 10h
0x1800042ac  cmp     esi, 0Eh
0x1800042af  jb      short loc_18000428B
0x1800042b1  mov     ebx, 80020009h
0x1800042b6  mov     rcx, rbp; pv
0x1800042b9  call    cs:__imp_CoTaskMemFree
0x1800042c0  nop     dword ptr [rax+rax+00h]
0x1800042c5  mov     eax, ebx
0x1800042c7  mov     rcx, [rsp+2088h+var_48]
0x1800042cf  xor     rcx, rsp; StackCookie
0x1800042d2  call    __security_check_cookie
0x1800042d7  mov     rbx, [rsp+2088h+arg_18]
0x1800042df  add     rsp, 2050h
0x1800042e6  pop     r15
0x1800042e8  pop     r14
0x1800042ea  pop     r13
0x1800042ec  pop     r12
0x1800042ee  pop     rdi
0x1800042ef  pop     rsi
0x1800042f0  pop     rbp
0x1800042f1  retn
0x1800042f3  add     rbx, rbx
0x1800042f6  mov     rsi, [r13+rbx*8+8]
0x1800042fb  test    rsi, rsi
0x1800042fe  jz      short loc_1800042B1
0x180004300  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004305  mov     rcx, rdi; this
0x180004308  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000430d  mov     ebx, eax
0x18000430f  test    eax, eax
0x180004311  js      short loc_1800042B6
0x180004313  mov     eax, 7Bh ; '{'
0x180004318  cmp     ax, [rsp+2088h+String1]
0x18000431d  jnz     short loc_1800042B1
0x18000431f  mov     [rsp+2088h+var_2068], r12d; int
0x180004324  mov     r8, rsi; HKEY
0x180004327  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000432c  mov     rcx, rdi; this
0x18000432f  test    r15d, r15d
0x180004332  jz      short loc_180004365
0x180004334  mov     r14, [rdi]
0x180004337  mov     r9d, r15d; int
0x18000433a  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000433f  mov     ebx, eax
0x180004341  test    eax, eax
0x180004343  jns     short loc_180004377
0x180004345  xor     r9d, r9d; int
0x180004348  mov     [rdi], r14
0x18000434b  mov     r8, rsi; HKEY
0x18000434e  mov     [rsp+2088h+var_2068], r12d; int
0x180004353  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180004358  mov     rcx, rdi; this
0x18000435b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180004360  jmp     loc_1800042B6
0x180004365  xor     r9d, r9d; int
0x180004368  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000436d  mov     ebx, eax
0x18000436f  test    eax, eax
0x180004371  js      loc_1800042B6
0x180004377  mov     r8, [rdi]
0x18000437a  movzx   edx, word ptr [r8]
0x18000437e  mov     ecx, edx
0x180004380  sub     ecx, 9
0x180004383  jz      short loc_180004394
0x180004385  sub     ecx, 1
0x180004388  jz      short loc_180004394
0x18000438a  sub     ecx, 3
0x18000438d  jz      short loc_180004394
0x18000438f  cmp     ecx, 13h
0x180004392  jnz     short loc_1800043A8
0x180004394  mov     rcx, r8; lpsz
0x180004397  call    cs:__imp_CharNextW
0x18000439e  nop     dword ptr [rax+rax+00h]
0x1800043a3  mov     [rdi], rax
0x1800043a6  jmp     short loc_180004377
0x1800043a8  cmp     r12w, dx
0x1800043ac  jnz     loc_18000426F
0x1800043b2  jmp     loc_1800042B6
```
