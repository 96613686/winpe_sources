# CommandArguments::GetOptionString(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,wchar_t const *,bool &)

- ea: `0x140011bbc`
- end: `0x140011cd3`
- name: `?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z`
- size: `279`
- prototype: ``
- caller_count: `10`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140010c90`
- `0x140010f08`
- `0x14001117c`
- `0x14001b75c`
- `0x14001c6b0`
- `0x14001cfd0`
- `0x140024c90`
- `0x140024e00`
- `0x1400274f0`
- `0x140027e70`

## callees

- `0x140010450`
- `0x140011904`
- `0x140011bbc`
- `0x140022cec`
- `0x140031810`

## pseudocode

```c
__int64 __fastcall CommandArguments::GetOptionString(_QWORD *a1, __int128 *a2, __int128 *a3, __int64 a4, _BYTE *a5)
{
  __int128 v6; // xmm1
  __int64 v8; // rbx
  __int64 result; // rax
  const wchar_t *Src; // rbx
  const char *v11; // [rsp+20h] [rbp-78h]
  __int128 v12; // [rsp+40h] [rbp-58h] BYREF
  __int128 v13; // [rsp+50h] [rbp-48h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+60h] [rbp-38h] BYREF
  __int64 v15; // [rsp+A0h] [rbp+8h] BYREF

  v6 = *a2;
  v12 = *a3;
  v13 = v6;
  CommandArguments::GetOption(a1, &v15, &v13, &v12);
  v8 = v15;
  if ( v15 == *a1 )
  {
    *a5 = 0;
    return a4;
  }
  else
  {
    if ( !*(_BYTE *)(v15 + 64) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids, 87);
      }
      Src = (const wchar_t *)(v8 + 32);
      if ( *((_QWORD *)Src + 3) > 7u )
        Src = *(const wchar_t **)Src;
      EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v11, 126, 0xAu, Src);
      throw (EvtException *)pExceptionObject;
    }
    *a5 = 1;
    result = v8 + 72;
    if ( *(_QWORD *)(v8 + 96) > 7u )
      return *(_QWORD *)result;
  }
  return result;
}

```

## disassembly

```asm
0x140011bbc  mov     rax, rsp
0x140011bbf  mov     [rax+10h], rbx
0x140011bc3  mov     [rax+18h], rsi
0x140011bc7  push    rdi
0x140011bc8  sub     rsp, 90h
0x140011bcf  movaps  xmm0, xmmword ptr [r8]
0x140011bd3  mov     rsi, r9
0x140011bd6  movaps  xmm1, xmmword ptr [rdx]
0x140011bd9  lea     r9, [rax-58h]
0x140011bdd  lea     r8, [rax-48h]
0x140011be1  movdqa  xmmword ptr [rax-58h], xmm0
0x140011be6  lea     rdx, [rax+8]
0x140011bea  movdqa  xmmword ptr [rax-48h], xmm1
0x140011bef  mov     rdi, rcx
0x140011bf2  call    ?GetOption@CommandArguments@@AEBA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; CommandArguments::GetOption(std::wstring_view,std::wstring_view)
0x140011bf7  mov     rbx, [rsp+98h+arg_0]
0x140011bff  cmp     rbx, [rdi]
0x140011c02  jnz     short loc_140011C17
0x140011c04  mov     rax, [rsp+98h+arg_20]
0x140011c0c  mov     byte ptr [rax], 0
0x140011c0f  mov     rax, rsi
0x140011c12  jmp     loc_140011CBE
0x140011c17  cmp     byte ptr [rbx+40h], 0
0x140011c1b  jnz     loc_140011CA5
0x140011c21  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c28  lea     rax, WPP_GLOBAL_Control
0x140011c2f  mov     edi, 57h ; 'W'
0x140011c34  cmp     rcx, rax
0x140011c37  jz      short loc_140011C5E
0x140011c39  test    dword ptr [rcx+1Ch], 400000h
0x140011c40  jz      short loc_140011C5E
0x140011c42  cmp     byte ptr [rcx+19h], 2
0x140011c46  jb      short loc_140011C5E
0x140011c48  mov     rcx, [rcx+10h]
0x140011c4c  lea     edx, [rdi-47h]
0x140011c4f  mov     r9d, edi
0x140011c52  lea     r8, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids
0x140011c59  call    WPP_SF_d
0x140011c5e  add     rbx, 20h ; ' '
0x140011c62  cmp     qword ptr [rbx+18h], 7
0x140011c67  jbe     short loc_140011C6C
0x140011c69  mov     rbx, [rbx]
0x140011c6c  mov     [rsp+98h+Src], rbx; Src
0x140011c71  lea     rcx, [rsp+98h+pExceptionObject]; this
0x140011c76  mov     [rsp+98h+var_68], 0Ah; unsigned int
0x140011c7e  xor     r9d, r9d; unsigned int
0x140011c81  xor     r8d, r8d; unsigned int
0x140011c84  mov     [rsp+98h+var_70], 7Eh ; '~'; int
0x140011c8c  mov     edx, edi; unsigned int
0x140011c8e  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140011c93  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140011c9a  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x140011c9f  call    _CxxThrowException_0
0x140011ca5  mov     rax, [rsp+98h+arg_20]
0x140011cad  mov     byte ptr [rax], 1
0x140011cb0  lea     rax, [rbx+48h]
0x140011cb4  cmp     qword ptr [rax+18h], 7
0x140011cb9  jbe     short loc_140011CBE
0x140011cbb  mov     rax, [rax]
0x140011cbe  lea     r11, [rsp+98h+var_8]
0x140011cc6  mov     rbx, [r11+18h]
0x140011cca  mov     rsi, [r11+20h]
0x140011cce  mov     rsp, r11
0x140011cd1  pop     rdi
0x140011cd2  retn
```
