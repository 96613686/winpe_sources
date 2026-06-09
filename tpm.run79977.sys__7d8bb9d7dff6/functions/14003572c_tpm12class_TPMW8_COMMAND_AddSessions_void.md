# tpm12class::TPMW8_COMMAND::AddSessions(void)

- ea: `0x14003572c`
- end: `0x1400357d5`
- name: `?AddSessions@TPMW8_COMMAND@tpm12class@@QEAAJXZ`
- size: `169`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400389a0`
- `0x140038ee0`

## callees

- `0x140031d2c`
- `0x1400321dc`
- `0x1400355c4`
- `0x14003572c`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_COMMAND::AddSessions(tpm12class::TPMW8_COMMAND *this)
{
  unsigned int v1; // edi
  __int64 result; // rax
  tpm12class::TPMW8_SESSION *v4; // rcx
  tpm12class::TPMW8_SESSION *v5; // rcx
  tpm12class::TPMW8_SESSION *v6; // rcx
  unsigned int v7; // edx

  v1 = *((_DWORD *)this + 4);
  *((_DWORD *)this + 17) = 0;
  *((_BYTE *)this + 48) = 1;
  result = tpm12class::TpmDataObject::AddData(this, 0);
  if ( (int)result >= 0 )
  {
    v4 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 21);
    *((_BYTE *)this + 48) = 0;
    if ( v4 )
    {
      tpm12class::TPMW8_SESSION::AddSession(v4, this);
      v5 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 22);
      if ( v5 )
      {
        tpm12class::TPMW8_SESSION::AddSession(v5, this);
        v6 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 23);
        if ( v6 )
          tpm12class::TPMW8_SESSION::AddSession(v6, this);
      }
      v7 = *((_DWORD *)this + 4) - v1 - 4;
      *((_DWORD *)this + 17) = v7;
      result = tpm12class::TpmDataObject::SetData(this, v7, v1);
      if ( (int)result >= 0 )
      {
        *((_DWORD *)this + 18) = *((_DWORD *)this + 4);
        if ( this == (tpm12class::TPMW8_COMMAND *)-80LL )
        {
          return 2147942487LL;
        }
        else
        {
          *((_DWORD *)this + 20) = *((_DWORD *)this + 10);
          return 0;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003572c  mov     [rsp+arg_0], rbx
0x140035731  push    rdi
0x140035732  sub     rsp, 20h
0x140035736  mov     edi, [rcx+10h]
0x140035739  xor     edx, edx; unsigned int
0x14003573b  mov     rbx, rcx
0x14003573e  mov     dword ptr [rcx+44h], 0
0x140035745  mov     byte ptr [rcx+30h], 1
0x140035749  call    ?AddData@TpmDataObject@tpm12class@@QEAAJI@Z; tpm12class::TpmDataObject::AddData(uint)
0x14003574e  test    eax, eax
0x140035750  js      short loc_1400357C9
0x140035752  mov     rcx, [rbx+0A8h]; this
0x140035759  mov     byte ptr [rbx+30h], 0
0x14003575d  test    rcx, rcx
0x140035760  jz      short loc_1400357C9
0x140035762  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x140035765  call    ?AddSession@TPMW8_SESSION@tpm12class@@QEAAJPEAVTpmDataObject@2@@Z; tpm12class::TPMW8_SESSION::AddSession(tpm12class::TpmDataObject *)
0x14003576a  mov     rcx, [rbx+0B0h]; this
0x140035771  test    rcx, rcx
0x140035774  jz      short loc_140035792
0x140035776  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x140035779  call    ?AddSession@TPMW8_SESSION@tpm12class@@QEAAJPEAVTpmDataObject@2@@Z; tpm12class::TPMW8_SESSION::AddSession(tpm12class::TpmDataObject *)
0x14003577e  mov     rcx, [rbx+0B8h]; this
0x140035785  test    rcx, rcx
0x140035788  jz      short loc_140035792
0x14003578a  mov     rdx, rbx; struct tpm12class::TpmDataObject *
0x14003578d  call    ?AddSession@TPMW8_SESSION@tpm12class@@QEAAJPEAVTpmDataObject@2@@Z; tpm12class::TPMW8_SESSION::AddSession(tpm12class::TpmDataObject *)
0x140035792  mov     edx, [rbx+10h]
0x140035795  mov     r8d, edi; unsigned int
0x140035798  sub     edx, edi
0x14003579a  mov     rcx, rbx; this
0x14003579d  add     edx, 0FFFFFFFCh; unsigned int
0x1400357a0  mov     [rbx+44h], edx
0x1400357a3  call    ?SetData@TpmDataObject@tpm12class@@QEAAJII@Z; tpm12class::TpmDataObject::SetData(uint,uint)
0x1400357a8  test    eax, eax
0x1400357aa  js      short loc_1400357C9
0x1400357ac  mov     eax, [rbx+10h]
0x1400357af  lea     rcx, [rbx+50h]
0x1400357b3  mov     [rbx+48h], eax
0x1400357b6  test    rcx, rcx
0x1400357b9  jnz     short loc_1400357C2
0x1400357bb  mov     eax, 80070057h
0x1400357c0  jmp     short loc_1400357C9
0x1400357c2  mov     eax, [rbx+28h]
0x1400357c5  mov     [rcx], eax
0x1400357c7  xor     eax, eax
0x1400357c9  mov     rbx, [rsp+28h+arg_0]
0x1400357ce  add     rsp, 20h
0x1400357d2  pop     rdi
0x1400357d3  retn
```
