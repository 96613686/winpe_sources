# SXWriter::commitStream(void)

- ea: `0x1004087e0`
- end: `0x10040882d`
- name: `?commitStream@SXWriter@@IEAAXXZ`
- size: `77`
- prototype: `void __fastcall(SXWriter *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1004082d0`
- `0x100408450`
- `0x1004086c0`
- `0x1004091c0`

## callees

- `0x100401350`
- `0x1004086f0`
- `0x1004087e0`
- `0x100424580`

## pseudocode

```c
void __fastcall SXWriter::commitStream(SXWriter *this)
{
  int v2; // eax

  if ( *((_QWORD *)this + 15) )
  {
    SXWriter::writeBuffer(this);
    if ( *((_BYTE *)this + 251) )
    {
      v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 15) + 64LL))(*((_QWORD *)this + 15), 0);
      if ( v2 < 0 )
      {
        _mm_lfence();
        MXRRaiseException(v2);
        JUMPOUT(0x10040882CLL);
      }
      *((_BYTE *)this + 251) = 0;
    }
  }
}

```

## disassembly

```asm
0x1004087e0  push    rbx
0x1004087e2  sub     rsp, 20h
0x1004087e6  cmp     qword ptr [rcx+78h], 0
0x1004087eb  mov     rbx, rcx
0x1004087ee  jz      short loc_10040881C
0x1004087f0  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x1004087f5  cmp     byte ptr [rbx+0FBh], 0
0x1004087fc  jz      short loc_10040881C
0x1004087fe  mov     rcx, [rbx+78h]
0x100408802  xor     edx, edx
0x100408804  mov     rax, [rcx]
0x100408807  mov     rax, [rax+40h]
0x10040880b  call    cs:__guard_dispatch_icall_fptr
0x100408811  test    eax, eax
0x100408813  js      short loc_100408822
0x100408815  mov     byte ptr [rbx+0FBh], 0
0x10040881c  add     rsp, 20h
0x100408820  pop     rbx
0x100408821  retn
0x100408822  lfence
0x100408825  mov     ecx, eax; int
0x100408827  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
