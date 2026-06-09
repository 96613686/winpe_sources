# CLdapBer::HrEndReadSequence(void)

- ea: `0x180001820`
- end: `0x1800018bc`
- name: `?HrEndReadSequence@CLdapBer@@QEAAKXZ`
- size: `156`
- prototype: `unsigned int __fastcall(CLdapBer *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800018d0`
- `0x180004740`
- `0x18001ba9c`
- `0x180031128`
- `0x180041e40`

## callees

- `0x180001820`
- `0x180003570`

## pseudocode

```c
unsigned int __fastcall CLdapBer::HrEndReadSequence(CLdapBer *this)
{
  int v1; // eax
  unsigned int v3; // eax
  __int64 v4; // rcx
  __int64 v5; // rax
  int v6; // edi
  int v7; // esi
  unsigned int result; // eax
  unsigned int v9; // ecx
  unsigned int v10; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 8);
  v10 = 0;
  if ( !v1 )
    return -2147024809;
  v3 = v1 - 1;
  *((_DWORD *)this + 8) = v3;
  v4 = v3;
  v5 = 2LL * v3;
  v6 = *((_DWORD *)this + 2 * v5 + 9);
  *((_DWORD *)this + 1) = v6;
  v7 = *((_DWORD *)this + 2 * v5 + 10);
  *((_DWORD *)this + 210) = *((_DWORD *)this + 2 * v5 + 11);
  *((_DWORD *)this + 209) = *((_DWORD *)this + 4 * v4 + 12);
  result = CLdapBer::HrGetLength(this, &v10);
  if ( !result )
  {
    v9 = v7 + v6 + v10;
    if ( v9 < v6 + v10 )
    {
      *((_DWORD *)this + 1) = -1;
    }
    else
    {
      *((_DWORD *)this + 1) = v9;
      if ( v9 <= *(_DWORD *)this )
        return result;
    }
    return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x180001820  push    rbx
0x180001822  sub     rsp, 20h
0x180001826  mov     eax, [rcx+20h]
0x180001829  mov     rbx, rcx
0x18000182c  mov     [rsp+28h+arg_0], 0
0x180001834  test    eax, eax
0x180001836  jz      short loc_1800018B5
0x180001838  dec     eax
0x18000183a  mov     [rsp+28h+arg_8], rsi
0x18000183f  mov     [rcx+20h], eax
0x180001842  lea     rdx, [rsp+28h+arg_0]; unsigned int *
0x180001847  mov     ecx, eax
0x180001849  add     rax, rax
0x18000184c  mov     [rsp+28h+arg_10], rdi
0x180001851  mov     edi, [rbx+rax*8+24h]
0x180001855  mov     [rbx+4], edi
0x180001858  mov     esi, [rbx+rax*8+28h]
0x18000185c  mov     eax, [rbx+rax*8+2Ch]
0x180001860  mov     [rbx+348h], eax
0x180001866  lea     rax, [rcx+3]
0x18000186a  add     rax, rax
0x18000186d  mov     rcx, rbx; this
0x180001870  mov     eax, [rbx+rax*8]
0x180001873  mov     [rbx+344h], eax
0x180001879  call    ?HrGetLength@CLdapBer@@QEAAKPEAK@Z; CLdapBer::HrGetLength(ulong *)
0x18000187e  test    eax, eax
0x180001880  jnz     short loc_18000189B
0x180001882  mov     edx, [rsp+28h+arg_0]
0x180001886  add     edx, edi
0x180001888  lea     ecx, [rsi+rdx]
0x18000188b  cmp     ecx, edx
0x18000188d  jb      short loc_1800018AC
0x18000188f  mov     [rbx+4], ecx
0x180001892  cmp     ecx, [rbx]
0x180001894  jbe     short loc_18000189B
0x180001896  mov     eax, 80070057h
0x18000189b  mov     rsi, [rsp+28h+arg_8]
0x1800018a0  mov     rdi, [rsp+28h+arg_10]
0x1800018a5  add     rsp, 20h
0x1800018a9  pop     rbx
0x1800018aa  retn
0x1800018ac  mov     dword ptr [rbx+4], 0FFFFFFFFh
0x1800018b3  jmp     short loc_180001896
0x1800018b5  mov     eax, 80070057h
0x1800018ba  jmp     short loc_1800018A5
```
