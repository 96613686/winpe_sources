# CImpWorkerWndProc::CreateWorkerWindow(HWND__ *,ulong,ulong,HMENU__ *)

- ea: `0x18001b78c`
- end: `0x18001b81c`
- name: `?CreateWorkerWindow@CImpWorkerWndProc@@IEAAPEAUHWND__@@PEAU2@KKPEAUHMENU__@@@Z`
- size: `144`
- prototype: `HWND __fastcall(CImpWorkerWndProc *__hidden this, HWND, unsigned int, unsigned int, HMENU)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b930`

## callees

- `0x18001b5b4`
- `0x18001b78c`

## import_xrefs

- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18001b7c8`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18001b80c`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18001b7c8`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18001b80c`

## pseudocode

```c
HWND __fastcall CImpWorkerWndProc::CreateWorkerWindow(CImpWorkerWndProc *this, HWND a2)
{
  HWND result; // rax

  result = (HWND)*((_QWORD *)this + 1);
  if ( !result )
  {
    if ( *((_BYTE *)this + 16) )
    {
      if ( *((_QWORD *)this + 4)
        && *((_QWORD *)this + 3)
        && (result = (HWND)SHCreateWorkerWindowW(CImpWorkerWndProc::s_WndProc, 0, 0, 0, 0, this),
            (*((_QWORD *)this + 1) = result) != 0) )
      {
        if ( *((_BYTE *)this + 16) )
        {
          CImpWorkerWndProc::AddWndRef(this);
          return (HWND)*((_QWORD *)this + 1);
        }
      }
      else
      {
        return 0;
      }
    }
    else
    {
      result = (HWND)SHCreateWorkerWindowW(CImpWorkerWndProc::s_WndProc, 0, 0, 0, 0, this);
      *((_QWORD *)this + 1) = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b78c  push    rbx
0x18001b78e  sub     rsp, 30h
0x18001b792  mov     rax, [rcx+8]
0x18001b796  mov     rbx, rcx
0x18001b799  test    rax, rax
0x18001b79c  jnz     short loc_18001B816
0x18001b79e  cmp     [rcx+10h], al
0x18001b7a1  jz      short loc_18001B7EF
0x18001b7a3  cmp     [rcx+20h], rax
0x18001b7a7  jz      short loc_18001B7EB
0x18001b7a9  cmp     [rcx+18h], rax
0x18001b7ad  jz      short loc_18001B7EB
0x18001b7af  mov     [rsp+38h+var_10], rcx
0x18001b7b4  xor     r9d, r9d
0x18001b7b7  lea     rcx, ?s_WndProc@CImpWorkerWndProc@@KA_JPEAUHWND__@@I_K_J@Z; CImpWorkerWndProc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001b7be  mov     [rsp+38h+var_18], rax
0x18001b7c3  xor     r8d, r8d
0x18001b7c6  xor     edx, edx
0x18001b7c8  call    cs:__imp_SHCreateWorkerWindowW
0x18001b7ce  mov     [rbx+8], rax
0x18001b7d2  test    rax, rax
0x18001b7d5  jz      short loc_18001B7EB
0x18001b7d7  cmp     byte ptr [rbx+10h], 0
0x18001b7db  jz      short loc_18001B816
0x18001b7dd  mov     rcx, rbx; this
0x18001b7e0  call    ?AddWndRef@CImpWorkerWndProc@@AEAAXXZ; CImpWorkerWndProc::AddWndRef(void)
0x18001b7e5  mov     rax, [rbx+8]
0x18001b7e9  jmp     short loc_18001B816
0x18001b7eb  xor     eax, eax
0x18001b7ed  jmp     short loc_18001B816
0x18001b7ef  mov     [rsp+38h+var_10], rbx
0x18001b7f4  lea     rcx, ?s_WndProc@CImpWorkerWndProc@@KA_JPEAUHWND__@@I_K_J@Z; CImpWorkerWndProc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001b7fb  xor     r9d, r9d
0x18001b7fe  mov     [rsp+38h+var_18], 0
0x18001b807  xor     r8d, r8d
0x18001b80a  xor     edx, edx
0x18001b80c  call    cs:__imp_SHCreateWorkerWindowW
0x18001b812  mov     [rbx+8], rax
0x18001b816  add     rsp, 30h
0x18001b81a  pop     rbx
0x18001b81b  retn
```
