# XML_RENDERER::AppendLockTimeout(unsigned __int64)

- ea: `0x1800141b4`
- end: `0x1800142b5`
- name: `?AppendLockTimeout@XML_RENDERER@@AEAAJ_K@Z`
- size: `257`
- prototype: `__int64 __fastcall(XML_RENDERER *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013bb0`

## callees

- `0x1800141b4`
- `0x18001c550`
- `0x180022520`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001420d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001420d`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180014266`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180014266`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001428e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001428e`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800141f7`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180014281`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800141f7`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180014281`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800141dd`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800141dd`

## pseudocode

```c
__int64 __fastcall XML_RENDERER::AppendLockTimeout(XML_RENDERER *this, unsigned __int64 a2)
{
  STRA *v4; // rdi
  int v5; // eax
  unsigned __int64 v6; // rdx
  int v7; // ebx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v10[56]; // [rsp+28h] [rbp-50h] BYREF

  STRA::STRA((STRA *)v10);
  if ( a2 == -1 )
  {
    v4 = (XML_RENDERER *)((char *)this + 24);
    v5 = STRA::Append((XML_RENDERER *)((char *)this + 24), "<D:timeout>Infinite</D:timeout>");
LABEL_9:
    v7 = v5;
    if ( v5 >= 0 && !*(_DWORD *)this )
      v7 = STRA::Append(v4, "\r\n");
    goto LABEL_12;
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( a2 >= *(_QWORD *)&SystemTimeAsFileTime )
  {
    v6 = (a2 - *(_QWORD *)&SystemTimeAsFileTime) / 0x989680;
    if ( v6 > 0xFFFFFFFF )
      LODWORD(v6) = -1;
  }
  else
  {
    LODWORD(v6) = 0;
  }
  v7 = SAFE_snprintf((struct STRA *)v10, "<D:timeout>Second-%lu</D:timeout>", v6);
  if ( v7 >= 0 )
  {
    v4 = (XML_RENDERER *)((char *)this + 24);
    v5 = STRA::Append((XML_RENDERER *)((char *)this + 24), (const struct STRA *)v10);
    goto LABEL_9;
  }
LABEL_12:
  STRA::~STRA((STRA *)v10);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800141b4  mov     [rsp+arg_10], rbx
0x1800141b9  mov     [rsp+arg_18], rsi
0x1800141be  push    rdi
0x1800141bf  sub     rsp, 70h
0x1800141c3  mov     rax, cs:__security_cookie
0x1800141ca  xor     rax, rsp
0x1800141cd  mov     [rsp+78h+var_18], rax
0x1800141d2  mov     rsi, rcx
0x1800141d5  mov     rbx, rdx
0x1800141d8  lea     rcx, [rsp+78h+var_50]
0x1800141dd  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800141e3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800141e7  jnz     short loc_1800141FF
0x1800141e9  lea     rdi, [rsi+18h]
0x1800141ed  mov     rcx, rdi
0x1800141f0  lea     rdx, aDTimeoutInfini; "<D:timeout>Infinite</D:timeout>"
0x1800141f7  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x1800141fd  jmp     short loc_18001426C
0x1800141ff  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014204  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001420d  call    cs:__imp_GetSystemTimeAsFileTime
0x180014213  cmp     rbx, qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x180014218  jnb     short loc_18001421E
0x18001421a  xor     edx, edx
0x18001421c  jmp     short loc_180014240
0x18001421e  sub     rbx, qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x180014223  mov     rax, 0D6BF94D5E57A42BDh
0x18001422d  mul     rbx
0x180014230  mov     eax, 0FFFFFFFFh
0x180014235  shr     rdx, 17h
0x180014239  cmp     rdx, rax
0x18001423c  jbe     short loc_180014240
0x18001423e  mov     edx, eax
0x180014240  mov     r8d, edx
0x180014243  lea     rcx, [rsp+78h+var_50]; struct STRA *
0x180014248  lea     rdx, aDTimeoutSecond; "<D:timeout>Second-%lu</D:timeout>"
0x18001424f  call    ?SAFE_snprintf@@YAJPEAVSTRA@@PEBDZZ; SAFE_snprintf(STRA *,char const *,...)
0x180014254  mov     ebx, eax
0x180014256  test    eax, eax
0x180014258  js      short loc_180014289
0x18001425a  lea     rdi, [rsi+18h]
0x18001425e  mov     rcx, rdi
0x180014261  lea     rdx, [rsp+78h+var_50]
0x180014266  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x18001426c  mov     ebx, eax
0x18001426e  test    eax, eax
0x180014270  js      short loc_180014289
0x180014272  cmp     dword ptr [rsi], 0
0x180014275  jnz     short loc_180014289
0x180014277  lea     rdx, asc_1800263B4; "\r\n"
0x18001427e  mov     rcx, rdi
0x180014281  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180014287  mov     ebx, eax
0x180014289  lea     rcx, [rsp+78h+var_50]
0x18001428e  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180014294  mov     eax, ebx
0x180014296  mov     rcx, [rsp+78h+var_18]
0x18001429b  xor     rcx, rsp; StackCookie
0x18001429e  call    __security_check_cookie
0x1800142a3  lea     r11, [rsp+78h+var_8]
0x1800142a8  mov     rbx, [r11+20h]
0x1800142ac  mov     rsi, [r11+28h]
0x1800142b0  mov     rsp, r11
0x1800142b3  pop     rdi
0x1800142b4  retn
```
