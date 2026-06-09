# CImpWorkerWndProc::CreateWorkerWindow(HWND__ *,ulong,ulong,HMENU__ *)

- ea: `0x18002dc3c`
- end: `0x18002dcd0`
- name: `?CreateWorkerWindow@CImpWorkerWndProc@@IEAAPEAUHWND__@@PEAU2@KKPEAUHMENU__@@@Z`
- size: `148`
- prototype: `HWND __fastcall(CImpWorkerWndProc *__hidden this, HWND, unsigned int, unsigned int, HMENU)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002dfa0`

## callees

- `0x18002dbe0`
- `0x18002dc3c`

## import_xrefs

- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18002dc7a`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18002dcc0`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18002dc7a`
- `SHLWAPI!__imp_SHCreateWorkerWindowW` at `0x18002dcc0`

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
        && (result = (HWND)SHCreateWorkerWindowW(CImpWorkerWndProc::s_WndProc, -3, 0),
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
      result = (HWND)SHCreateWorkerWindowW(CImpWorkerWndProc::s_WndProc, -3, 0);
      *((_QWORD *)this + 1) = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002dc3c  push    rbx
0x18002dc3e  sub     rsp, 30h
0x18002dc42  mov     rax, [rcx+8]
0x18002dc46  mov     rbx, rcx
0x18002dc49  test    rax, rax
0x18002dc4c  jnz     short loc_18002DCCA
0x18002dc4e  cmp     [rcx+10h], al
0x18002dc51  jz      short loc_18002DCA1
0x18002dc53  cmp     [rcx+20h], rax
0x18002dc57  jz      short loc_18002DC9D
0x18002dc59  cmp     [rcx+18h], rax
0x18002dc5d  jz      short loc_18002DC9D
0x18002dc5f  mov     [rsp+38h+var_10], rcx
0x18002dc64  lea     rdx, [rax-3]
0x18002dc68  lea     rcx, ?s_WndProc@CImpWorkerWndProc@@KA_JPEAUHWND__@@I_K_J@Z; CImpWorkerWndProc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18002dc6f  mov     [rsp+38h+var_18], rax
0x18002dc74  xor     r9d, r9d
0x18002dc77  xor     r8d, r8d
0x18002dc7a  call    cs:__imp_SHCreateWorkerWindowW
0x18002dc80  mov     [rbx+8], rax
0x18002dc84  test    rax, rax
0x18002dc87  jz      short loc_18002DC9D
0x18002dc89  cmp     byte ptr [rbx+10h], 0
0x18002dc8d  jz      short loc_18002DCCA
0x18002dc8f  mov     rcx, rbx; this
0x18002dc92  call    ?AddWndRef@CImpWorkerWndProc@@AEAAXXZ; CImpWorkerWndProc::AddWndRef(void)
0x18002dc97  mov     rax, [rbx+8]
0x18002dc9b  jmp     short loc_18002DCCA
0x18002dc9d  xor     eax, eax
0x18002dc9f  jmp     short loc_18002DCCA
0x18002dca1  xor     r9d, r9d
0x18002dca4  mov     [rsp+38h+var_10], rbx
0x18002dca9  xor     r8d, r8d
0x18002dcac  mov     [rsp+38h+var_18], 0
0x18002dcb5  lea     rcx, ?s_WndProc@CImpWorkerWndProc@@KA_JPEAUHWND__@@I_K_J@Z; CImpWorkerWndProc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18002dcbc  lea     rdx, [r9-3]
0x18002dcc0  call    cs:__imp_SHCreateWorkerWindowW
0x18002dcc6  mov     [rbx+8], rax
0x18002dcca  add     rsp, 30h
0x18002dcce  pop     rbx
0x18002dccf  retn
```
