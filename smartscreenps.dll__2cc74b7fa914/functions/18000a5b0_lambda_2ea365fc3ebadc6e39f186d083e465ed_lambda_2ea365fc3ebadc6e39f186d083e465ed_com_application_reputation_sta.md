# _lambda_2ea365fc3ebadc6e39f186d083e465ed_::_lambda_2ea365fc3ebadc6e39f186d083e465ed_(com::application_reputation_static *,IInspectable * * &)

- ea: `0x18000a5b0`
- end: `0x18000a5bb`
- name: `??0_lambda_2ea365fc3ebadc6e39f186d083e465ed_@@QEAA@PEAVapplication_reputation_static@com@@AEAPEAPEAUIInspectable@@@Z`
- size: `11`
- prototype: `_lambda_2ea365fc3ebadc6e39f186d083e465ed_ *__fastcall(_lambda_2ea365fc3ebadc6e39f186d083e465ed_ *__hidden this, struct com::application_reputation_static *, struct IInspectable ***)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000ad00`

## pseudocode

```c
_lambda_2ea365fc3ebadc6e39f186d083e465ed_ *__fastcall _lambda_2ea365fc3ebadc6e39f186d083e465ed_::_lambda_2ea365fc3ebadc6e39f186d083e465ed_(
        _lambda_2ea365fc3ebadc6e39f186d083e465ed_ *this,
        struct com::application_reputation_static *a2,
        struct IInspectable ***a3)
{
  _lambda_2ea365fc3ebadc6e39f186d083e465ed_ *result; // rax

  *(_QWORD *)this = a2;
  result = this;
  *((_QWORD *)this + 1) = a3;
  return result;
}

```

## disassembly

```asm
0x18000a5b0  mov     [rcx], rdx
0x18000a5b3  mov     rax, rcx
0x18000a5b6  mov     [rcx+8], r8
0x18000a5ba  retn
```
