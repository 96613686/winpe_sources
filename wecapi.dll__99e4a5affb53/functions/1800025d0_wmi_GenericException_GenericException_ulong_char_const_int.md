# wmi::GenericException::GenericException(ulong,char const *,int)

- ea: `0x1800025d0`
- end: `0x1800025fd`
- name: `??0GenericException@wmi@@QEAA@KPEBDH@Z`
- size: `45`
- prototype: `__int64 __fastcall(wmi::GenericException *__hidden this, unsigned int, const char *, int)`
- caller_count: `38`
- callee_count: `0`
- tags: ``

## callers

- `0x18000262c`
- `0x1800027ec`
- `0x180002900`
- `0x180002a14`
- `0x1800036fc`
- `0x180003870`
- `0x180004510`
- `0x180004640`
- `0x180004780`
- `0x180004940`
- `0x180004b50`
- `0x180004cc0`
- `0x180004ec0`
- `0x180005220`
- `0x1800054c0`
- `0x1800057b0`
- `0x180005900`
- `0x180005a00`
- `0x180005b90`
- `0x180005f18`
- `0x18000632c`
- `0x1800066c4`
- `0x180006818`
- `0x180006b88`
- `0x180006fb8`
- `0x1800073c4`
- `0x1800075e0`
- `0x180007720`
- `0x180007aa0`
- `0x18000908c`
- `0x18000996c`
- `0x18000a820`
- `0x18000acec`
- `0x18000aea4`
- `0x18000b540`
- `0x18000b6b8`
- `0x18000b804`
- `0x18000b880`

## pseudocode

```c
wmi::GenericException *__fastcall wmi::GenericException::GenericException(
        wmi::GenericException *this,
        int a2,
        const char *a3,
        int a4)
{
  wmi::GenericException *result; // rax

  *((_QWORD *)this + 2) = a3;
  *((_BYTE *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *(_QWORD *)this = &wmi::GenericException::`vftable';
  result = this;
  *((_DWORD *)this + 10) = a2;
  *((_DWORD *)this + 11) = -1;
  *((_DWORD *)this + 12) = a4;
  return result;
}

```

## disassembly

```asm
0x1800025d0  xor     eax, eax
0x1800025d2  mov     [rcx+10h], r8
0x1800025d6  mov     [rcx+8], al
0x1800025d9  mov     [rcx+18h], rax
0x1800025dd  mov     [rcx+20h], rax
0x1800025e1  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800025e8  mov     [rcx], rax
0x1800025eb  mov     rax, rcx
0x1800025ee  mov     [rcx+28h], edx
0x1800025f1  mov     dword ptr [rcx+2Ch], 0FFFFFFFFh
0x1800025f8  mov     [rcx+30h], r9d
0x1800025fc  retn
```
