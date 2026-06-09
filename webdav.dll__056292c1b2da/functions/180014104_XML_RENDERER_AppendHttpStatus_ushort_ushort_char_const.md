# XML_RENDERER::AppendHttpStatus(ushort,ushort,char const *)

- ea: `0x180014104`
- end: `0x1800141ab`
- name: `?AppendHttpStatus@XML_RENDERER@@AEAAJGGPEBD@Z`
- size: `167`
- prototype: `__int64 __fastcall(XML_RENDERER *__hidden this, unsigned __int16, unsigned __int16, const char *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800145a8`
- `0x180014fa0`

## callees

- `0x180014104`
- `0x18001a648`
- `0x18001c550`
- `0x180022520`

## import_xrefs

- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18001417e`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18001417e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001418b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001418b`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18001412c`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18001412c`

## pseudocode

```c
__int64 __fastcall XML_RENDERER::AppendHttpStatus(const char **this, unsigned __int16 a2, __int64 a3, const char *a4)
{
  int v5; // esi
  int v7; // ebx
  _BYTE v9[56]; // [rsp+40h] [rbp-58h] BYREF

  v5 = a2;
  STRA::STRA((STRA *)v9);
  if ( !a4 )
    a4 = MapHttpStatusToDescription(v5);
  v7 = SAFE_snprintf(
         (struct STRA *)v9,
         "<D:status>HTTP/%u.%u %u %s</D:status>%s",
         *((unsigned __int16 *)this + 40),
         *((unsigned __int16 *)this + 41),
         v5,
         a4,
         this[1]);
  if ( v7 >= 0 )
    v7 = STRA::Append((STRA *)(this + 3), (const struct STRA *)v9);
  STRA::~STRA((STRA *)v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180014104  push    rbx
0x180014106  push    rsi
0x180014107  push    rdi
0x180014108  sub     rsp, 80h
0x18001410f  mov     rax, cs:__security_cookie
0x180014116  xor     rax, rsp
0x180014119  mov     [rsp+98h+var_20], rax
0x18001411e  mov     rdi, rcx
0x180014121  movzx   esi, dx
0x180014124  lea     rcx, [rsp+98h+var_58]
0x180014129  mov     rbx, r9
0x18001412c  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014132  test    rbx, rbx
0x180014135  jnz     short loc_180014142
0x180014137  movzx   ecx, si; unsigned __int16
0x18001413a  call    ?MapHttpStatusToDescription@@YAPEBDG@Z; MapHttpStatusToDescription(ushort)
0x18001413f  mov     rbx, rax
0x180014142  mov     rcx, [rdi+8]
0x180014146  lea     rdx, aDStatusHttpUUU; "<D:status>HTTP/%u.%u %u %s</D:status>%s"
0x18001414d  movzx   r9d, word ptr [rdi+52h]
0x180014152  movzx   r8d, word ptr [rdi+50h]
0x180014157  mov     [rsp+98h+var_68], rcx
0x18001415c  lea     rcx, [rsp+98h+var_58]; struct STRA *
0x180014161  mov     [rsp+98h+var_70], rbx
0x180014166  mov     [rsp+98h+var_78], esi
0x18001416a  call    ?SAFE_snprintf@@YAJPEAVSTRA@@PEBDZZ; SAFE_snprintf(STRA *,char const *,...)
0x18001416f  mov     ebx, eax
0x180014171  test    eax, eax
0x180014173  js      short loc_180014186
0x180014175  lea     rcx, [rdi+18h]
0x180014179  lea     rdx, [rsp+98h+var_58]
0x18001417e  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x180014184  mov     ebx, eax
0x180014186  lea     rcx, [rsp+98h+var_58]
0x18001418b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180014191  mov     eax, ebx
0x180014193  mov     rcx, [rsp+98h+var_20]
0x180014198  xor     rcx, rsp; StackCookie
0x18001419b  call    __security_check_cookie
0x1800141a0  add     rsp, 80h
0x1800141a7  pop     rdi
0x1800141a8  pop     rsi
0x1800141a9  pop     rbx
0x1800141aa  retn
```
