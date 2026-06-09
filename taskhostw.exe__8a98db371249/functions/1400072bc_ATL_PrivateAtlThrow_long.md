# ATL::PrivateAtlThrow(long)

- ea: `0x1400072bc`
- end: `0x140007321`
- name: `?PrivateAtlThrow@ATL@@YAXJ@Z`
- size: `101`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x140001ef0`
- `0x140002040`
- `0x1400022d0`
- `0x140002970`
- `0x140002b40`
- `0x140002e30`
- `0x140003130`
- `0x140005d50`
- `0x140006770`
- `0x1400068f0`
- `0x140006c10`
- `0x140006d90`
- `0x140007298`
- `0x140009850`
- `0x1400098d0`
- `0x140009ab8`

## callees

- `0x1400072bc`
- `0x140007f24`
- `0x14000894c`

## pseudocode

```c
void __fastcall __noreturn ATL::PrivateAtlThrow(int a1)
{
  char *v2; // rax
  char *pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  v2 = (char *)operator new(0x38u);
  pExceptionObject = v2;
  if ( v2 )
  {
    v2[8] = 0;
    *(_QWORD *)v2 = &wmi::GenericException::`vftable';
    *((_QWORD *)v2 + 2) = &qword_14000F9E0;
    *((_QWORD *)v2 + 3) = 0;
    *((_QWORD *)v2 + 4) = 0;
    *((_DWORD *)v2 + 10) = a1;
    *(_QWORD *)(v2 + 44) = -1;
  }
  else
  {
    v2 = 0;
  }
  pExceptionObject = v2;
  throw (wmi::GenericException **)&pExceptionObject;
}

```

## disassembly

```asm
0x1400072bc  push    rbx
0x1400072be  sub     rsp, 20h
0x1400072c2  mov     ebx, ecx
0x1400072c4  mov     ecx, 38h ; '8'; Size
0x1400072c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400072ce  xor     edx, edx
0x1400072d0  mov     [rsp+28h+pExceptionObject], rax
0x1400072d5  test    rax, rax
0x1400072d8  jz      short loc_140007307
0x1400072da  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1400072e1  mov     [rax+8], dl
0x1400072e4  mov     [rax], rcx
0x1400072e7  lea     rcx, qword_14000F9E0
0x1400072ee  mov     [rax+10h], rcx
0x1400072f2  mov     [rax+18h], rdx
0x1400072f6  mov     [rax+20h], rdx
0x1400072fa  mov     [rax+28h], ebx
0x1400072fd  mov     qword ptr [rax+2Ch], 0FFFFFFFFFFFFFFFFh
0x140007305  jmp     short loc_14000730A
0x140007307  mov     rax, rdx
0x14000730a  lea     rdx, _TI4PEAVGenericException@wmi@@; pThrowInfo
0x140007311  mov     [rsp+28h+pExceptionObject], rax
0x140007316  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14000731b  call    _CxxThrowException_0
```
