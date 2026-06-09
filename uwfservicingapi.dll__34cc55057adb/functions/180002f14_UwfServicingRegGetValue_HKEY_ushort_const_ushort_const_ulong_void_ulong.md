# UwfServicingRegGetValue(HKEY__ *,ushort const *,ushort const *,ulong *,void * *,ulong *)

- ea: `0x180002f14`
- end: `0x180002ffa`
- name: `?UwfServicingRegGetValue@@YAJPEAUHKEY__@@PEBG1PEAKPEAPEAX2@Z`
- size: `230`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *pdwType, void **, unsigned int *pcbData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180002960`
- `0x180002db0`

## callees

- `0x180002f14`

## import_xrefs

- `msvcrt!malloc` at `0x180002f8d`
- `msvcrt!malloc` at `0x180002f8d`
- `msvcrt!free` at `0x180002fcc`
- `msvcrt!free` at `0x180002fcc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002f67`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002fbd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002f67`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002fbd`

## pseudocode

```c
LSTATUS __fastcall UwfServicingRegGetValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *pdwType,
        void **a5,
        unsigned int *pcbData)
{
  LSTATUS result; // eax
  void *pvData; // rax
  void *v11; // rdi
  LSTATUS ValueW; // ebx

  *a5 = 0;
  *pcbData = 0;
  result = RegGetValueW(HKEY_LOCAL_MACHINE, a2, a3, 0xFFFFu, pdwType, 0, pcbData);
  if ( !result || result == 234 )
  {
    if ( *pcbData && (pvData = malloc(*pcbData), (v11 = pvData) != 0) )
    {
      ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, a2, a3, 0xFFFFu, pdwType, pvData, pcbData);
      if ( ValueW )
      {
        free(v11);
        if ( ValueW > 0 )
          return (unsigned __int16)ValueW | 0x80070000;
      }
      else
      {
        *a5 = v11;
      }
      return ValueW;
    }
    else
    {
      return -2147024888;
    }
  }
  else if ( result > 0 )
  {
    return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180002f14  push    rbx
0x180002f16  push    rbp
0x180002f17  push    rsi
0x180002f18  push    rdi
0x180002f19  push    r14
0x180002f1b  push    r15
0x180002f1d  sub     rsp, 48h
0x180002f21  mov     rbx, [rsp+78h+arg_28]
0x180002f29  mov     rbp, r9
0x180002f2c  mov     rsi, [rsp+78h+arg_20]
0x180002f34  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180002f3b  mov     [rsp+78h+pcbData], rbx; pcbData
0x180002f40  mov     r14, r8
0x180002f43  mov     [rsp+78h+pvData], 0; pvData
0x180002f4c  mov     r15, rdx
0x180002f4f  mov     [rsp+78h+pdwType], r9; pdwType
0x180002f54  mov     r9d, 0FFFFh; dwFlags
0x180002f5a  mov     qword ptr [rsi], 0
0x180002f61  mov     dword ptr [rbx], 0
0x180002f67  call    cs:__imp_RegGetValueW
0x180002f6d  test    eax, eax
0x180002f6f  jz      short loc_180002F86
0x180002f71  cmp     eax, 0EAh
0x180002f76  jz      short loc_180002F86
0x180002f78  test    eax, eax
0x180002f7a  jle     short loc_180002FED
0x180002f7c  movzx   eax, ax
0x180002f7f  or      eax, 80070000h
0x180002f84  jmp     short loc_180002FED
0x180002f86  cmp     dword ptr [rbx], 0
0x180002f89  jz      short loc_180002FE8
0x180002f8b  mov     ecx, [rbx]; Size
0x180002f8d  call    cs:__imp_malloc
0x180002f93  mov     rdi, rax
0x180002f96  test    rax, rax
0x180002f99  jz      short loc_180002FE8
0x180002f9b  mov     [rsp+78h+pcbData], rbx; pcbData
0x180002fa0  mov     r9d, 0FFFFh; dwFlags
0x180002fa6  mov     [rsp+78h+pvData], rax; pvData
0x180002fab  mov     r8, r14; lpValue
0x180002fae  mov     rdx, r15; lpSubKey
0x180002fb1  mov     [rsp+78h+pdwType], rbp; pdwType
0x180002fb6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180002fbd  call    cs:__imp_RegGetValueW
0x180002fc3  mov     ebx, eax
0x180002fc5  test    eax, eax
0x180002fc7  jz      short loc_180002FE1
0x180002fc9  mov     rcx, rdi; Block
0x180002fcc  call    cs:__imp_free
0x180002fd2  test    ebx, ebx
0x180002fd4  jle     short loc_180002FE4
0x180002fd6  movzx   ebx, bx
0x180002fd9  or      ebx, 80070000h
0x180002fdf  jmp     short loc_180002FE4
0x180002fe1  mov     [rsi], rdi
0x180002fe4  mov     eax, ebx
0x180002fe6  jmp     short loc_180002FED
0x180002fe8  mov     eax, 80070008h
0x180002fed  add     rsp, 48h
0x180002ff1  pop     r15
0x180002ff3  pop     r14
0x180002ff5  pop     rdi
0x180002ff6  pop     rsi
0x180002ff7  pop     rbp
0x180002ff8  pop     rbx
0x180002ff9  retn
```
