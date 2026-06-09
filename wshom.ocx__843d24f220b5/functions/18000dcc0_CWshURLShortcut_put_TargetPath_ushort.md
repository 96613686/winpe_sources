# CWshURLShortcut::put_TargetPath(ushort *)

- ea: `0x18000dcc0`
- end: `0x18000ddd7`
- name: `?put_TargetPath@CWshURLShortcut@@UEAAJPEAG@Z`
- size: `279`
- prototype: `__int64 __fastcall(CWshURLShortcut *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800059f8`
- `0x180005d20`
- `0x180006124`
- `0x18000dcc0`
- `0x180010250`
- `0x1800102e0`
- `0x180011010`

## string_xrefs

- `0x18000dd8a`: `WshURLShortcut.TargetPath`

## pseudocode

```c
__int64 __fastcall CWshURLShortcut::put_TargetPath(CWshURLShortcut *this, unsigned __int16 *a2)
{
  bool v2; // zf
  int v5; // ebx
  int v6; // eax
  char *v8; // [rsp+30h] [rbp-1028h] BYREF
  void *Block; // [rsp+38h] [rbp-1020h] BYREF
  char v10[4096]; // [rsp+40h] [rbp-1018h] BYREF

  v2 = *((_QWORD *)this + 9) == 0;
  Block = 0;
  v8 = 0;
  if ( v2 )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    v5 = PWSZToPSZ(a2, v10, 4096, (char **)&Block, &v8);
    if ( v5 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64))(**((_QWORD **)this + 9) + 24LL))(
             *((_QWORD *)this + 9),
             v8,
             1);
      v5 = v6;
      if ( v6 >= 0 )
      {
        v5 = 0;
      }
      else
      {
        switch ( v6 )
        {
          case -2147217407:
            Signal_Exception(&IID_IWshURLShortcut, L"WshURLShortcut.TargetPath", 0x1009u, a2);
            break;
          case -2147217406:
            Signal_Exception(&IID_IWshURLShortcut, L"WshURLShortcut.TargetPath", 0x100Au, a2);
            break;
          case -2147213310:
            Signal_Exception(&IID_IWshURLShortcut, L"WshURLShortcut.TargetPath", 0x1008u, a2);
            break;
        }
      }
    }
    if ( Block )
      operator delete(Block);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000dcc0  mov     [rsp+arg_10], rbx
0x18000dcc5  mov     [rsp+arg_18], rsi
0x18000dcca  push    rdi
0x18000dccb  mov     eax, 1050h
0x18000dcd0  call    _alloca_probe
0x18000dcd5  sub     rsp, rax
0x18000dcd8  mov     rax, cs:__security_cookie
0x18000dcdf  xor     rax, rsp
0x18000dce2  mov     [rsp+1058h+var_18], rax
0x18000dcea  cmp     qword ptr [rcx+48h], 0
0x18000dcef  mov     rdi, rdx
0x18000dcf2  mov     rsi, rcx
0x18000dcf5  mov     [rsp+1058h+Block], 0
0x18000dcfe  mov     [rsp+1058h+var_1028], 0
0x18000dd07  jnz     short loc_18000DD13
0x18000dd09  mov     ebx, 80004005h
0x18000dd0e  jmp     loc_18000DDB0
0x18000dd13  lea     rax, [rsp+1058h+var_1028]
0x18000dd18  mov     r8d, 1000h; int
0x18000dd1e  lea     r9, [rsp+1058h+Block]; char **
0x18000dd23  mov     [rsp+1058h+var_1038], rax; char **
0x18000dd28  lea     rdx, [rsp+1058h+var_1018]; char *
0x18000dd2d  mov     rcx, rdi; lpWideCharStr
0x18000dd30  call    ?PWSZToPSZ@@YAJPEBGPEADJPEAPEAD2@Z; PWSZToPSZ(ushort const *,char *,long,char * *,char * *)
0x18000dd35  mov     ebx, eax
0x18000dd37  test    eax, eax
0x18000dd39  js      short loc_18000DDA1
0x18000dd3b  mov     rcx, [rsi+48h]
0x18000dd3f  mov     r8d, 1
0x18000dd45  mov     rdx, [rsp+1058h+var_1028]
0x18000dd4a  mov     rax, [rcx]
0x18000dd4d  mov     rax, [rax+18h]
0x18000dd51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd56  mov     ebx, eax
0x18000dd58  test    eax, eax
0x18000dd5a  jns     short loc_18000DD9F
0x18000dd5c  cmp     eax, 80041001h
0x18000dd61  jz      short loc_18000DD81
0x18000dd63  cmp     eax, 80041002h
0x18000dd68  jz      short loc_18000DD79
0x18000dd6a  cmp     eax, 80042002h
0x18000dd6f  jnz     short loc_18000DDA1
0x18000dd71  mov     r8d, 1008h
0x18000dd77  jmp     short loc_18000DD87
0x18000dd79  mov     r8d, 100Ah
0x18000dd7f  jmp     short loc_18000DD87
0x18000dd81  mov     r8d, 1009h; unsigned int
0x18000dd87  mov     r9, rdi
0x18000dd8a  lea     rdx, aWshurlshortcut_0; "WshURLShortcut.TargetPath"
0x18000dd91  lea     rcx, IID_IWshURLShortcut; struct _GUID *
0x18000dd98  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x18000dd9d  jmp     short loc_18000DDA1
0x18000dd9f  xor     ebx, ebx
0x18000dda1  mov     rcx, [rsp+1058h+Block]; Block
0x18000dda6  test    rcx, rcx
0x18000dda9  jz      short loc_18000DDB0
0x18000ddab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ddb0  mov     eax, ebx
0x18000ddb2  mov     rcx, [rsp+1058h+var_18]
0x18000ddba  xor     rcx, rsp; StackCookie
0x18000ddbd  call    __security_check_cookie
0x18000ddc2  lea     r11, [rsp+1058h+var_8]
0x18000ddca  mov     rbx, [r11+20h]
0x18000ddce  mov     rsi, [r11+28h]
0x18000ddd2  mov     rsp, r11
0x18000ddd5  pop     rdi
0x18000ddd6  retn
```
