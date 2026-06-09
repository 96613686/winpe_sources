# WusaLogDebugEventA

- ea: `0x140013490`
- end: `0x14001359d`
- name: `WusaLogDebugEventA`
- size: `269`
- prototype: `__int64(_QWORD, _QWORD, const char *, ...)`
- caller_count: `58`
- callee_count: `4`
- tags: ``

## callers

- `0x140005794`
- `0x140005860`
- `0x140005b20`
- `0x140005c70`
- `0x140006554`
- `0x140006a44`
- `0x140006fb8`
- `0x1400075b0`
- `0x1400087e4`
- `0x140008ff8`
- `0x14000a4bc`
- `0x14000ab54`
- `0x14000afc0`
- `0x14000b84c`
- `0x14000c488`
- `0x14000d25c`
- `0x14000d44c`
- `0x14000d620`
- `0x14000db50`
- `0x14000e280`
- `0x14000e360`
- `0x14000e4c4`
- `0x14000e5f4`
- `0x14000e78c`
- `0x14000e9ac`
- `0x14000eb0c`
- `0x14000ec58`
- `0x14000ee88`
- `0x14000f240`
- `0x14000f294`
- `0x14000f45c`
- `0x14000f674`
- `0x14000f6f4`
- `0x14000f8f0`
- `0x14000fdf8`
- `0x140010800`
- `0x1400108dc`
- `0x140010aa0`
- `0x140010c94`
- `0x140010e88`
- `0x140011004`
- `0x140011190`
- `0x14001150c`
- `0x14001181c`
- `0x140011b08`
- `0x140011c10`
- `0x140011d18`
- `0x140011dcc`
- `0x1400121f0`
- `0x140012320`

## callees

- `0x1400044e0`
- `0x140013490`
- `0x1400135a4`
- `0x140014910`

## import_xrefs

- `ADVAPI32!EventEnabled` at `0x1400134db`
- `ADVAPI32!EventEnabled` at `0x1400134db`
- `msvcrt!_vsnprintf` at `0x140013509`
- `msvcrt!_vsnprintf` at `0x140013509`

## pseudocode

```c
__int64 WusaLogDebugEventA(__int64 a1, int a2, const char *a3, ...)
{
  int v5; // ebx
  unsigned int v6; // eax
  int v8; // [rsp+20h] [rbp-C38h]
  char Buffer[1023]; // [rsp+30h] [rbp-C28h] BYREF
  char v10; // [rsp+42Fh] [rbp-829h]
  unsigned __int16 v11[1024]; // [rsp+430h] [rbp-828h] BYREF
  va_list ArgList; // [rsp+C78h] [rbp+20h] BYREF

  va_start(ArgList, a3);
  if ( !RegHandle || !EventEnabled(RegHandle, &WUSA_EVENT_DEBUG) )
    return 0;
  v5 = 0;
  v8 = 0;
  v6 = _vsnprintf(Buffer, 0x3FFu, a3, ArgList);
  if ( v6 >= 0x400 )
  {
    v10 = 0;
    v5 = -2147024774;
    v8 = -2147024774;
  }
  else if ( v6 == 1023 )
  {
    v10 = 0;
  }
  if ( v5 >= 0 )
  {
    v5 = StringCchPrintfW(v11, 0x400u, L"%S", Buffer, v8, 0);
    if ( v5 >= 0 )
    {
      v5 = WusaLogDebugEventW(a1, a2, v11);
      if ( v5 >= 0 )
        return 0;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140013490  mov     [rsp+Format], r8
0x140013495  mov     qword ptr [rsp+ArgList], r9
0x14001349a  push    rbx
0x14001349b  push    rsi
0x14001349c  push    rdi
0x14001349d  sub     rsp, 0C40h
0x1400134a4  mov     rax, cs:__security_cookie
0x1400134ab  xor     rax, rsp
0x1400134ae  mov     [rsp+0C58h+var_28], rax
0x1400134b6  mov     esi, edx
0x1400134b8  mov     rdi, rcx
0x1400134bb  mov     [rsp+0C58h+var_C30], 0
0x1400134c4  mov     rcx, cs:RegHandle; RegHandle
0x1400134cb  test    rcx, rcx
0x1400134ce  jz      loc_14001357E
0x1400134d4  lea     rdx, WUSA_EVENT_DEBUG; EventDescriptor
0x1400134db  call    cs:__imp_EventEnabled
0x1400134e1  test    al, al
0x1400134e3  jz      loc_14001357E
0x1400134e9  lea     r9, [rsp+0C58h+ArgList]; ArgList
0x1400134f1  xor     ebx, ebx
0x1400134f3  mov     [rsp+0C58h+var_C38], ebx
0x1400134f7  mov     r8, [rsp+0C58h+Format]; Format
0x1400134ff  mov     edx, 3FFh; BufferCount
0x140013504  lea     rcx, [rsp+0C58h+Buffer]; Buffer
0x140013509  call    cs:__imp__vsnprintf
0x14001350f  test    eax, eax
0x140013511  js      short loc_140013525
0x140013513  cmp     eax, 3FFh
0x140013518  ja      short loc_140013525
0x14001351a  jnz     short loc_140013535
0x14001351c  mov     [rsp+0C58h+var_829], bl
0x140013523  jmp     short loc_140013535
0x140013525  mov     [rsp+0C58h+var_829], bl
0x14001352c  mov     ebx, 8007007Ah
0x140013531  mov     [rsp+0C58h+var_C38], ebx
0x140013535  mov     [rsp+0C58h+var_C30], 0
0x14001353e  test    ebx, ebx
0x140013540  js      short loc_140013580
0x140013542  lea     r9, [rsp+0C58h+Buffer]
0x140013547  lea     r8, aS_1; "%S"
0x14001354e  mov     edx, 400h; unsigned __int64
0x140013553  lea     rcx, [rsp+0C58h+var_828]; unsigned __int16 *
0x14001355b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140013560  mov     ebx, eax
0x140013562  test    eax, eax
0x140013564  js      short loc_140013580
0x140013566  lea     r8, [rsp+0C58h+var_828]
0x14001356e  mov     edx, esi
0x140013570  mov     rcx, rdi
0x140013573  call    WusaLogDebugEventW
0x140013578  mov     ebx, eax
0x14001357a  test    eax, eax
0x14001357c  js      short loc_140013580
0x14001357e  xor     ebx, ebx
0x140013580  mov     eax, ebx
0x140013582  mov     rcx, [rsp+0C58h+var_28]
0x14001358a  xor     rcx, rsp; StackCookie
0x14001358d  call    __security_check_cookie
0x140013592  add     rsp, 0C40h
0x140013599  pop     rdi
0x14001359a  pop     rsi
0x14001359b  pop     rbx
0x14001359c  retn
0x140014a96  push    rbp
0x140014a98  sub     rsp, 20h
0x140014a9c  mov     rbp, rdx
0x140014a9f  add     rsp, 20h
0x140014aa3  pop     rbp
0x140014aa4  retn
```
